---
name: Find an emergency-duty (akuttvakt) clinic in a county
description: List the clinics that offer emergency dental treatment outside normal hours in a Norwegian county, and hand the user a phone number to confirm.
api: openapi/finn-tannlege-com-openapi.yml
operations: [listDentalAgents, getDentalAgent]
generated: '2026-09-19'
method: generated
---

# Find an emergency-duty (akuttvakt) clinic in a county

Base URL: `https://finn-tannlege.com/api/tannlege`. No credentials are needed.

## Steps

1. **Filter for emergency duty.** Call `listDentalAgents` (`GET /api/tannlege/agents`) with
   `acute_vakt=1` and the county in `fylke` (e.g. `fylke=Rogaland`). Add `q` with a city to narrow
   further (`q=Stavanger`). The MCP tool `tannlege_akutt` is this exact call with `acute_vakt` fixed.
2. **Fall back to the wider county** if the page is empty: drop `q` and keep `fylke`; if still empty, drop
   `fylke` and tell the user that the directory lists no emergency-duty clinic nearby rather than guessing.
3. **Read the profile** with `getDentalAgent` (`GET /api/tannlege/agents/{id}`) to get `telefon`,
   `adresse`, `poststed` and `hjemmeside`.
4. **Tell the user to call first.** The provider's own guidance is "Ring alltid for å bekrefte
   åpningstider" — emergency hours vary by municipality and are usually evenings and weekends. Present the
   phone number as the primary action; municipal emergency dental services (kommunal tannlegevakt) are
   outside this directory.

## Rules

- `acute_vakt` is an integer flag (`1`) on REST and a boolean (`akutt`) on MCP; `null` on a profile means
  unknown, not "no".
- Respect the shared per-IP budget of 1000 requests per 15 minutes; read `RateLimit-Remaining`
  (`../rate-limits/finn-tannlege-com-rate-limits.yml`).
- Errors and conventions: `../errors/finn-tannlege-com-problem-types.yml`,
  `../conventions/finn-tannlege-com-conventions.yml`.
