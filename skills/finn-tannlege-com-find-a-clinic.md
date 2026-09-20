---
name: Find a dental clinic and read its profile
description: Search Norwegian dental clinics by place, county, specialty or Helfo agreement, then fetch one clinic's full profile and its registered specialists.
api: openapi/finn-tannlege-com-openapi.yml
operations: [listDentalAgents, discoverDentalAgents, getDentalAgent, getDentalSpecialists]
generated: '2026-09-19'
method: generated
---

# Find a dental clinic and read its profile

Base URL: `https://finn-tannlege.com/api/tannlege`. No credentials are needed for any step.

## Steps

1. **Search.** Call `listDentalAgents` (`GET /api/tannlege/agents`) with the filters you have:
   `q` (free text — clinic name or city, Norwegian or English), `fylke` (county name such as `Oslo`,
   `Vestland`, `Trøndelag`), `specialty` (a slug such as `kjeveortopedi`, `endodonti`, `periodonti`),
   `helfo=true` (Helfo direct-billing clinics only). Set `limit` (default 50, max 500) and page with
   `offset`. The response is `{count, agents[]}` where `count` is the size of this page, not the total —
   keep paging until a page comes back short.
   - If you only need ids, names and verification status, `discoverDentalAgents`
     (`GET /api/tannlege/discover`) takes the same filters and returns a slimmer `{count, results[]}`.
2. **Read the profile.** Take `id` (a UUID) from a result and call `getDentalAgent`
   (`GET /api/tannlege/agents/{id}`). Do not put the 9-digit `org_nr` in the path — it is a field on the
   clinic, not a path id; an unknown id returns `404 {"error":"Not found"}`.
3. **Read the specialists.** Call `getDentalSpecialists` (`GET /api/tannlege/agents/{id}/specialists`) for
   the HPR-registered specialists at that clinic. `available_specialties` on the profile is the summary;
   this call is the detail.
4. **Present with provenance.** Show `verification_status` (`verified` is an editorially set badge;
   `needs_review` and `pending_verify` clinics are listed but unreviewed) and `updated_at`. Link the human
   page `https://finn-tannlege.com/klinikk/{name-slug}-{org_nr}` rather than the API URL.

## Rules

- **Rate limit:** 1000 requests per 15 minutes per IP, shared with the A2A and MCP surfaces. Read
  `RateLimit-Remaining` and `RateLimit-Reset` on every response and slow down before they reach zero
  (see `../rate-limits/finn-tannlege-com-rate-limits.yml`).
- **Errors:** only a flat `{"error": "..."}` on 404; invalid query values are silently defaulted, not
  rejected — validate `limit` yourself (see `../errors/finn-tannlege-com-problem-types.yml`).
- **Read-only:** there is nothing to undo; no idempotency key exists or is needed
  (see `../conventions/finn-tannlege-com-conventions.yml`).
- **Language:** response field names are Norwegian (`navn`, `poststed`, `fylke`, `adresse`, `telefon`,
  `hjemmeside`); free-text input may be Norwegian or English.
