# simplegenius.co.uk

One-page marketing site for **Simple Genius** — a trading name of Tenfold Ltd — which builds focused Shopify apps (**Tax Inside** and **+Tax**).

Static HTML/CSS, no build step. ElevenLabs-inspired design.

## Files
- `index.html` — homepage
- `privacy-policy.html`, `terms-of-service.html` — legal pages
- `brain.txt` — hero Lottie animation (hosted as `.txt`; cPanel's editor JSON-linter chokes on large `.json`)

## Deployment
Hosted on HostArmada cPanel (account `simplegeniusco`). Deploys automatically via
**GitHub Actions → FTPS** on every push to `main` (`.github/workflows/deploy.yml`).

```
edit → commit → push  →  live in ~60s
```

The workflow uses [SamKirkland/FTP-Deploy-Action](https://github.com/SamKirkland/FTP-Deploy-Action)
and a dedicated cPanel FTP account whose home directory **is** `public_html`, so files
upload straight to the web root (`server-dir: ./`). It needs three repo secrets
(Settings → Secrets and variables → Actions):

| Secret | Value |
|---|---|
| `FTP_SERVER` | `lon1.hostclusters.com` |
| `FTP_USERNAME` | the dedicated FTP account, e.g. `deploy@simplegenius.co.uk` |
| `FTP_PASSWORD` | its password |

To deploy without a code change: repo → **Actions** → *Deploy to HostArmada* → **Run workflow**.

> Note: cPanel's native Git™ Version Control does **not** work here — HostArmada's shared
> server blocks outbound connections to github.com, so it clones empty. `.cpanel.yml`
> remains in the repo but is unused by the active pipeline.
