# Static site production audit

Audit date: 2026-09-07  
Scope: generated `_site` artifact for the Console Repair Canada sister site at `https://consolerepair.ca`, adapted from the graphicsrepair-ca architecture. Repeat the same six locales, legal routes, GitHub Pages artifact deploy and DNS-only Cloudflare posture.

## Repeatable gate

Run these from the repository root:

```bash
python3 build_console_site.py --check
node --check site/assets/site.js
node --test tests/test_lead_payload.js
python3 tests/test_console_site.py
```

## Intentional boundaries

- Re-thermals and cleaning start at $90 plus tax on an accepted PlayStation, Xbox or Nintendo Switch. Extra work is quoted separately. International clients are billed in USD. The public site does not claim CAD. This is not a repair diagnostic and does not promise temperatures, noise or a resolved fault.
- Laptop GPU repair and phone repair are outside this intake.
- Drop-offs are welcome whenever MRC is open; the site does not claim appointments are scheduled.
- Notomo site ID 2 is never reused. The dedicated `consolerepair.ca` property uses full session replay, including literal form values.
- Playwright/WASM browser tests are kept in the tree for local use but are not part of GitHub Actions on `ubuntu-latest`.
