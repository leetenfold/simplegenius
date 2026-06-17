# simplegenius.co.uk

One-page marketing site for **Simple Genius** — a trading name of Tenfold Ltd — which builds focused Shopify apps (**Tax Inside** and **+Tax**).

Static HTML/CSS, no build step. ElevenLabs-inspired design.

## Files
- `index.html` — homepage
- `privacy-policy.html`, `terms-of-service.html` — legal pages
- `brain.txt` — hero Lottie animation (hosted as `.txt`; cPanel's editor JSON-linter chokes on large `.json`)

## Deployment
Hosted on HostArmada cPanel (account `simplegeniusco`). Deploys via **cPanel Git™ Version Control**:
push to GitHub, then in cPanel → Git Version Control, *Update from Remote* → *Deploy HEAD Commit*.
`.cpanel.yml` copies the deployable files into `public_html/`.
