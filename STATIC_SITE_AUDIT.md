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

- The $50 CAD plus tax service is named Console Certification. It records factual observations about an accepted used PlayStation, Xbox or Nintendo Switch / handheld console. It is not a repair diagnostic, authenticity guarantee, performance guarantee, warranty or legal determination of fraud.
- Laptop GPU repair and phone repair are outside this intake.
- Drop-offs are welcome whenever MRC is open; the site does not claim appointments are scheduled.
- Notomo site ID 2 is never reused. The dedicated `consolerepair.ca` property uses full session replay, including literal form values.
- Playwright/WASM browser tests are kept in the tree for local use but are not part of GitHub Actions on `ubuntu-latest`.
