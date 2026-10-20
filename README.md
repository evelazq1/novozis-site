# novozis.com

One-page static site for Novozis Cyber Security, hosted on GitHub Pages.

## Files

- `index.html` — the whole site (HTML, CSS and the small form script in one file)
- `favicon.svg` — browser tab icon
- `CNAME` — tells GitHub Pages to serve the site at novozis.com
- `.nojekyll` — serve files as-is (no Jekyll build)

## Making changes

Edit `index.html` and push to `main`. GitHub Pages republishes in about a minute.
To make changes through Claude, ask Claude in the Novozis project to update the site; it edits this repo and pushes the commit.

## Contact form

The form posts to Web3Forms, which emails each submission to the address linked to the access key.
The key is the `access_key` value in `index.html`. It is designed to be public; spam is filtered by Web3Forms plus the hidden `botcheck` field.

## One-time setup

1. Create a Web3Forms access key at web3forms.com using the shared inbox (e.g. hello@novozis.com), and paste it into `index.html`.
2. Create a GitHub repo (e.g. `novozis/novozis.com`), add these files, push to `main`.
3. Repo Settings → Pages → Deploy from branch `main`, folder `/ (root)`. Custom domain: `novozis.com`.
4. At the domain's DNS provider, replace the website records only (leave MX/email records alone):
   - `A` @ → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - `AAAA` @ → 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153
   - `CNAME` www → `<github-user-or-org>.github.io`
5. Once the domain check passes in Settings → Pages, tick "Enforce HTTPS" (can take up to 24 hours to become available).
