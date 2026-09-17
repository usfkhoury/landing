# Agent notes — landing_page

Personal landing page at **usfkhoury.com**. Pure static: no build step, no
JS framework, no dependencies. Netlify publishes the repo root as-is.

## Facts

- **Single page**: `index.html` (self-contained: inline CSS + JS).
- **Media**: two orientation-specific tribute videos in `assets/`
  (`tribute-landscape.mp4`, `tribute-portrait.mp4`). The page picks one via
  a `matchMedia` orientation query.
- **Deploy**: push to `main` → Netlify serves the repo root. No config file
  needed; nothing to build.
- **No env vars, no backend, no analytics.**

## When editing

- Change copy/style/layout by editing `index.html` directly.
- Replacing a video: keep the same filename and roughly the same aspect
  ratio, or update the `<source>` tags in `index.html`.
- Do not add a build tool or package.json — this repo's whole point is
  "one HTML file". If a change wants a build step, push back.

## Deep context

Historical ADRs and design notes were removed from the repo. Nothing is
archived — the site is small enough to be self-describing from `index.html`.
