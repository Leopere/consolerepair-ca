# Project infrastructure direction

- Treat references to `leadform` and Woodpecker as legacy context, not as the default architecture.
- Prefer Cloudflare Workers for runtime services, including protected form handling.
- Prefer GitHub Actions on `ubuntu-latest` for automation and GitHub Pages artifact deployment.
- Use the dedicated Notomo property ID `consolerepair.ca`; never reuse motherboardrepair.ca's site ID `2`. Keep full session replay enabled for this property, including literal repair-form values.
- Confirm current production state before following older notes or names.
- Keep `motherboardrepair-ca` and `graphicsrepair-ca` read-only when using them as architectural references.
