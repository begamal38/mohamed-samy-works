# Mohamed Samy Works — Official Website

Static production website for **Mohamed Samy Works** (`https://www.mohamedsamyworks.com/`), hosted on Cloudflare Pages from this repo (`main` auto-deploys).

## Structure
- `index.html` — single page (Three.js scroll scene, project gallery with zoom & pan). Project data lives in the `PROJECTS` array.
- `assets/v2/*.webp` — real project photos (up to 2048 px), re-exported from the original shoots in `E:\محمد سامي\سامية\website` and `E:\محمد سامي\After 8` (After 8 kept as delivered).
- `assets/v2/sm/*.webp` — 800 px copies used by cards, thumbnails and grid tiles (the full file loads only in the zoom stage).
- `assets/v2/og-cover.jpg` — 1200×630 share image for Facebook / WhatsApp previews.
- `assets/v2/site.<hash>.css` — compiled Tailwind CSS (no Tailwind CDN at runtime).
- `_headers` — caching, HSTS, security headers, `noindex` on `*.pages.dev`.
- `_redirects` — `/works/<project-id>`, `/about`, `/campaigns`… rewrite to the page; anything else returns `404.html`.

## After editing classes in index.html, rebuild the CSS
```
npx tailwindcss@3.4.17 -c tailwind.config.js -i in.css -o assets/v2/site.<newhash>.css --minify
```
(config: content `index.html` + `404.html`, colors obsidian/charcoal/surface/crimson/crimson-dark, font Inter). Use a new file name each time, because `/assets/*` is cached for a year, and update the `<link>` in `index.html` and `404.html`.

## Adding a project
Add an entry at the top of `PROJECTS` (newest first), put photos in `assets/v2/` and `assets/v2/sm/`, then update the counts (hero stats, nav, filters, regions card, JSON-LD `ItemList`, `sitemap.xml`).
