---
name: Query the directory through A2A or MCP instead of REST
description: Discover the agent card, send a natural-language search over A2A message/send, or open an MCP session and call the five read-only tools.
api: openapi/finn-tannlege-com-openapi.yml
operations: [getDentalAgentCardWellKnown, dentalA2AJsonRpc, dentalMcpStreamableHttp, getLlmsTxt]
generated: '2026-09-19'
method: generated
---

# Query the directory through A2A or MCP instead of REST

Both agent surfaces are anonymous and are thin fronts over the same REST routes; pick whichever your
runtime already speaks. Details: `../a2a/finn-tannlege-com-a2a.yml`, `../mcp/finn-tannlege-com-mcp.yml`,
`../mcp/finn-tannlege-com-tool-crosswalk.yml`.

## A2A

1. **Discover.** `getDentalAgentCardWellKnown` (`GET /.well-known/agent-card.json`) returns the signed
   card: `url` is `https://finn-tannlege.com/a2a`, three skills (`tannlege_search`, `tannlege_info`,
   `tannlege_stats`), `preferredTransport` JSONRPC. `getLlmsTxt` (`GET /llms.txt`) carries a cURL example.
2. **Send.** `dentalA2AJsonRpc` (`POST /a2a`) with a JSON-RPC 2.0 `message/send` whose text part is a
   natural-language query in Norwegian or English (`"finn tannlege med helfo-avtale i Oslo"`,
   `"find orthodontist in Bergen"`) or a JSON object such as `{"org_nr": "912345678"}` for `tannlege_info`.
3. **Read the task.** The result is a completed task with two artifacts: a bilingual text summary and a
   data part `{count, clinics[]}`. `metadata.skill` and `metadata.filter` show how the query was parsed;
   check them before trusting an empty result.
4. **Do not call anything else.** `tasks/get`, `tasks/cancel` and `message/stream` return JSON-RPC
   `-32601` over HTTP 200; the card's `capabilities` are all `false`.

## MCP

1. **Initialize.** `dentalMcpStreamableHttp` (`POST /mcp`) with `initialize`
   (`Accept: application/json, text/event-stream`). Read the `Mcp-Session-Id` response header. The
   server negotiated protocol `2025-06-18` on 2026-09-19.
2. **Echo the session** on every later request (`Mcp-Session-Id` header) and send
   `notifications/initialized`. Without it every call answers HTTP 404, `-32001 "Session not found"`.
3. **List and call tools.** `tools/list` returns `tannlege_search`, `tannlege_info`, `tannlege_stats`,
   `tannlege_akutt`, `tannlege_kjeder`, each annotated `readOnlyHint: true`. `tannlege_info` accepts
   `org_nr` directly, which the REST path does not. `tannlege_stats` has no REST equivalent.
4. **Prefer the URL for hosted agents; `npx finn-tannlege-mcp` only for a local desktop client.** Both are
   the same 0.1.0 server.

## Rules

- One shared budget: 1000 requests per 15 minutes per IP across REST, A2A and MCP — read
  `RateLimit-Remaining` on every response (`../rate-limits/finn-tannlege-com-rate-limits.yml`).
- Everything is read-only; the optional `X-API-Key` (`POST /api/keys`, free, no account) only labels your
  calls in the provider's usage ledger and does not raise the limit
  (`../conventions/finn-tannlege-com-conventions.yml`).
