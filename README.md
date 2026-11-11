# tinymuesli-site

The homepage for [tinyMuesli](https://github.com/PotentialHedge/tinymuesli), at
<https://tinymuesli.potentialhedge.com> (muesli.potentialhedge.com redirects there).

Astro, deployed to GitHub Pages by `.github/workflows/deploy.yml` on every push to `main`.
Astro needs Node 24 (`.node-version`).

```sh
npm install
npm run dev       # http://localhost:4321
npm run build     # → dist/
```

- **Analytics:** Umami at analytics.potentialhedge.com (website "tinyMuesli", id in
  `src/layouts/Base.astro`). Only production builds load it. Buttons send the events
  `download-click`, `github-click` and `install-copy`.
- **DNS (Cloudflare, zone potentialhedge.com):** `tinymuesli` is a DNS-only CNAME to
  `potentialhedge.github.io` (GitHub issues the certificate). `muesli` is a proxied record
  plus a redirect rule that sends it to tinymuesli.potentialhedge.com with a 301.
- **Download button:** links to `releases/latest/download/tinyMuesli.dmg`, which the app's
  `scripts/release.sh` uploads with each release.
