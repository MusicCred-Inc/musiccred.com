# musiccred.com

Public website for MusicCred, Inc. Plain static HTML, hosted on GitHub Pages from the `main` branch (root). No build step, no framework, no dependencies.

## Pages

| URL | File | Notes |
|---|---|---|
| `/` | `index.html` | Home |
| `/about/` | `about/index.html` | About + founder |
| `/support/` | `support/index.html` | Support & FAQ (the apps link here) |
| `/privacy-policy/` | `privacy-policy/index.html` | Privacy Policy — this exact URL is on the App Store listing |
| `/tos/` | `tos/index.html` | Terms of Service (the apps link here) |
| `/404.html` | `404.html` | Served by GitHub Pages for unknown paths |

Shared assets: `styles.css`, `favicon.svg`. The header/footer markup is repeated in each page on purpose (no templating), so an edit to the nav or footer has to be made in all five pages.

Legacy / alternate URLs (`/about.html`, `/support.html`, `/privacy.html`, `/privacy-policy.html`, `/privacy/`, `/terms.html`, `/terms/`, `/terms-of-service/`) are tiny redirect stubs pointing at the canonical URLs above. Keep them; old links in emails and app builds still use some of them.

## Editing

Edit the HTML directly and commit to `main`; GitHub Pages redeploys in about a minute. Keep these in mind:

- Contact address everywhere is `support@musiccred.com` (an alias on Google Workspace).
- The legal pages are the April 25, 2023 versions, reproduced verbatim. Any change to them goes through counsel first.
- Do not add claims about patents. The provisional patent applications lapsed in 2024.
- Deep links for the mobile apps are configured for `app.musiccred.com`, not this host. When the platform is rebuilt, that host must serve `/.well-known/assetlinks.json` and `/.well-known/apple-app-site-association`.

## Hosting and DNS

- `CNAME` contains `musiccred.com`; GitHub Pages custom domain is set to the same value.
- `.nojekyll` disables Jekyll processing.
- DNS is managed at Wix (nameservers `ns8/ns9.wixdns.net`). Apex `A` records point at GitHub Pages (`185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`); `www` is a `CNAME` to `musiccred-inc.github.io`. Mail (MX, SPF, DKIM, DMARC) stays on Google Workspace.

`robots.txt` and `sitemap.xml` list the five canonical pages.
