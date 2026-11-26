# Mohamed Samy Works — Official Website

Static production website for **Mohamed Samy Works** (`https://www.mohamedsamyworks.com/`).

## Structure
- `index.html` — Main single-page application (Tailwind CDN, Three.js 3D architectural scroll scene, interactive full-viewport zoom & pan gallery).
- `assets/*.webp` — 156 high-resolution lazy-loaded real project photos + official logo.
- `_headers` — Cloudflare Pages caching rules for instant repeat loads.

## Deploy to Cloudflare Pages
1. Push this folder to a GitHub repository.
2. In Cloudflare Dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
3. Select the repository with:
   - **Framework preset:** None
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`
4. Under **Custom domains**, add `mohamedsamyworks.com` and `www.mohamedsamyworks.com`.
