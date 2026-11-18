# 52 Saturdays — landing page

Static, dependency-free landing page for *52 Saturdays* by Case Morton.
No build step: open `index.html` or serve the folder from any static host.

```
index.html        page markup
css/site.css      all styles (brand tokens in :root at the top)
js/main.js        all behavior (ES module, no libraries)
assets/           artwork, photos, PDF (WebP where possible)
fonts/            self-hosted WOFF2: Barlow Condensed, DM Sans, Space Mono, Kalam
```

## Run locally

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```

## Deploy

GitHub Pages: Settings → Pages → Deploy from branch → `main` / root.
Works the same on Netlify, Vercel or Cloudflare Pages (no build command, publish directory `/`).

## Before launch

| What | Where |
| --- | --- |
| Trailer | currently a "Coming soon" panel (`.poster.is-soon`); swap back to a `<button class="poster" data-video="…">` when ready |
| Vertical clips | `data-video="…"` on each `.vclip` button (an `.mp4` path or an embed URL) |
| Retreat | currently a condensed "Coming soon" card (`.ev-soon`); add dates there when set |
| Waitlist form | `TODO` in the waitlist section of `js/main.js`: send the form data to your email service |
| Placeholder copy | anything starting with "Add…" or "NAME" in `index.html` |
| Social links | footer `.social` links in `index.html` |

## Notes

- Fonts and images are self-hosted; the page makes no third-party requests.
- Motion respects `prefers-reduced-motion`.
- Images below the fold use `loading="lazy"`; the book cover is preloaded.
