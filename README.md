# Rackbops legal pages

Public, static pages served by GitHub Pages at <https://legal.rackbops.com/>:

- `/` -- app home page for **research-triage** (the name must match the app name on its Google OAuth consent screen).
- `/privacy/` -- privacy policy.
- `/terms/` -- terms of service.

Why this exists: Google's OAuth brand verification needs a publicly readable home page,
privacy policy and terms on an authorized domain. Everything else on `rackbops.com` sits
behind Cloudflare Access, so those pages live here instead, on a hostname that is not
proxied through Access (`legal` is a DNS-only CNAME to `rackbops.github.io`).

Plain HTML, no build step (`.nojekyll`). Edit the HTML, commit to `main`, Pages redeploys.
When a policy changes, bump the "Effective" date on the page.

Other Rackbops apps that need a Google consent screen can add their own section to the
home page and their own policy pages here rather than standing up a second site.
