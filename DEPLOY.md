# Runneth Labs site

Plain static HTML/CSS. No build step.

## Current preview (temporary)
- https://coherent-tide-c3fbr59.shipstatic.com (anonymous ShipStatic deploy, expires Oct 31, 2026 2:58 PM MST unless claimed; claim link kept in .ship-claim.txt, not committed)
- Redeploy: rm -rf dist && mkdir dist && cp index.html privacy.html terms.html 404.html style.css favicon.svg og.png robots.txt dist/ && npx -y @shipstatic/ship ./dist --json

## Permanent host (recommended): GitHub Pages
After `gh auth login` (one-time device code):
  gh repo create runneth-labs-site --public --source . --push
  gh api -X POST repos/{owner}/runneth-labs-site/pages -f 'source[branch]=main' -f 'source[path]=/'
After buying the domain: add a CNAME file with the domain, push, then add the DNS records below.

## DNS records for GitHub Pages (apex + www)
A     @    185.199.108.153
A     @    185.199.109.153
A     @    185.199.110.153
A     @    185.199.111.153
AAAA  @    2606:50c0:8000::153
AAAA  @    2606:50c0:8001::153
AAAA  @    2606:50c0:8002::153
AAAA  @    2606:50c0:8003::153
CNAME www  <github-username>.github.io

## TODOs
- Contact email is likeaustinpowers@gmail.com (the Google account that owns the Runneth Sync for Jira add-on). Swap it for a domain address later if wanted.
- Once the domain is live, make og:image absolute and add <link rel="canonical">.

## Pages
- runneth-sync.html: Runneth Sync for Jira product and support page (also its Marketplace support URL).
- privacy.html / terms.html: these must match the add-on's real data handling and OAuth scopes (see sheets-addon-jirasync/SCOPES.md). Update both together.
