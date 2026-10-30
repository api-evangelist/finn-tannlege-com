# Finn-tannlege

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Finn-tannlege.com is an independent, free directory of Norwegian dental clinics (5,447 clinics on 2026-09-19) assembled from public sources - the Brønnøysund Register Centre (Brreg), the Norwegian Health Personnel Register (HPR), the Norwegian Dental Association (NTF) and the clinics' own websites - and searchable by county (fylke), specialty, Helfo direct-billing agreement and emergency-duty (akuttvakt) availability. It is built for people and AI agents alike: an open, key-free REST API under /api/tannlege described by an OpenAPI 3.1 document, an A2A 1.0.0 agent card and JSON-RPC endpoint, a remote Streamable-HTTP MCP server plus an npm stdio package (finn-tannlege-mcp), an llms.txt and a ChatGPT Custom GPT. Operated by Daniel Fredriksen on the same Norwegian A2A agent platform as rettfrabonden.com and opplevagent.no; every clinic field is stored with its source and last-confirmed date, and the "Verified" badge is an editorially set status.

**Areas:** Dental · Healthcare · Directory · Norway · Search · Open Data · A2A · MCP · AI Agents · Clinics

## Finn-tannlege on APIs.io

Everything profiled for Finn-tannlege is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/finn-tannlege-com/](https://apis.io/providers/finn-tannlege-com/)** — or go straight to one of the APIs or properties below.

### APIs (7)

- [Finn-tannlege A2A Agent](https://apis.io/apis/finn-tannlege-com/finn-tannlege-a2a-agent/) — The agent-to-agent surface: an anonymous A2A JSON-RPC 2.0 endpoint at https://finn-tannlege.com/a2a implementing message/send, described by a signed (EdDSA…
- [Finn-tannlege MCP Server](https://apis.io/apis/finn-tannlege-com/finn-tannlege-mcp-server/) — Model Context Protocol server in two shipped forms: a remote Streamable-HTTP endpoint at https://finn-tannlege.com/mcp (session-based - initialize first,…
- [Finn-tannlege A2a API](https://apis.io/apis/finn-tannlege-com/finn-tannlege-com-a2a-api/) — The A2a API from Finn-tannlege — 1 operation(s) for a2a.
- [Finn-tannlege Llms.txt API](https://apis.io/apis/finn-tannlege-com/finn-tannlege-com-llms-txt-api/) — The Llms.txt API from Finn-tannlege — 1 operation(s) for llms.txt.
- [Finn-tannlege MCP API](https://apis.io/apis/finn-tannlege-com/finn-tannlege-com-mcp-api/) — The Mcp API from Finn-tannlege — 1 operation(s) for mcp.
- [Finn-tannlege Tannlege API](https://apis.io/apis/finn-tannlege-com/finn-tannlege-com-tannlege-api/) — The Tannlege API from Finn-tannlege — 5 operation(s) for tannlege.
- [Finn-tannlege .well Known API](https://apis.io/apis/finn-tannlege-com/finn-tannlege-com-well-known-api/) — The .well Known API from Finn-tannlege — 1 operation(s) for .well known.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [finn-tannlege](https://apis.io/servers/finn-tannlege-com/finn-tannlege/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Finn Tannlege Com Agentic Access](https://apis.io/agentic-access/finn-tannlege-com/finn-tannlege-com-agentic-access/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Finn Tannlege Com Openapi Overlay](https://apis.io/overlays/finn-tannlege-com/finn-tannlege-com-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Finn Tannlege Com Authentication](https://apis.io/security/finn-tannlege-com/finn-tannlege-com-authentication/)
- [Finn Tannlege Com Domain Security](https://apis.io/security/finn-tannlege-com/finn-tannlege-com-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Finn Tannlege Com Plans Pricing](https://apis.io/plans/finn-tannlege-com/finn-tannlege-com-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Finn Tannlege Com Rate Limits](https://apis.io/rate-limits/finn-tannlege-com/finn-tannlege-com-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://finn-tannlege.com/)
- [Documentation](https://finn-tannlege.com/llms.txt)
- [Getting started](https://finn-tannlege.com/hvordan-det-fungerer)
- [Pricing](https://finn-tannlege.com/hvordan-det-fungerer)
- [Support](https://finn-tannlege.com/kontakt)
- [Privacy policy](https://finn-tannlege.com/personvern)

## API Evangelist rating

**Kin Score 40.6** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 42.6 |
| Contract governance | 18.2 |
| Operational transparency | 26.3 |
| Developer ergonomics | 39.9 |
| Access clarity | 42.1 |

**Agent readiness 35.1** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 19.5** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/finn-tannlege-com/](https://apis.io/providers/finn-tannlege-com/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Finn-tannlege: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/finn-tannlege-com/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
