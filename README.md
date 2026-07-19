# Precise Infer — Landing Page

Static marketing site for **Precise Infer** — inference optimization for AI product teams.

## Files

- `index.html` — the page. Self-contained apart from three external loads: Google Fonts, the [Pretext](https://github.com/chenglou/pretext) text-layout engine (`pretext.js`, local), and the Cal.com booking popup.
- `pretext.js` — text-layout engine. Must sit next to `index.html` (loaded via `import './pretext.js'`).

## Local preview

Module imports need HTTP — opening the file over `file://` won't run the layout/booking layer. Serve it:

```
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Deploy

Hosted on **GitHub Pages**. A push to `index.html` on `main` triggers
`.github/workflows/deploy.yml`, which publishes the site via GitHub's
`deploy-pages` action. Pages source must be set to **GitHub Actions**
(Settings → Pages → Build and deployment → Source).

## Booking

All "Book a 20-minute call" buttons open a Cal.com popup. The calendar is set by
the `CAL_LINK` constant near the bottom of `index.html`.
