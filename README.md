# usfkhoury.com — Personal Hub

Landing page at **[usfkhoury.com](https://usfkhoury.com)** linking to the two sub-projects: a Lebanese cooking blog and a family olive grove tracker.

Deployed on Netlify. Single static `index.html` — no build step.

## Design

Warm-Mediterranean aesthetic: Fraunces display serif (Google Fonts), bone/espresso palette, terracotta accent. Split two-column layout on desktop, centered column on mobile. Olive-sprig SVG draws in on load; all animations respect `prefers-reduced-motion`.

## Theme

Three modes cycled by the `◐` button (top-right corner):

| Mode | Behaviour |
|---|---|
| **auto** | Follows OS `prefers-color-scheme` |
| **light** | Warm bone palette |
| **dark** | Espresso dark palette |

Choice is persisted to `localStorage`. A no-flash script in `<head>` applies the saved theme before first paint.

## Editing

Open `index.html`. Everything — markup, styles, scripts — lives in that one file.

The only external dependency is Fraunces from Google Fonts. To remove that dependency, download a latin-subset `fraunces.woff2`, drop it in `/fonts/`, and replace the `<link>` tags with an `@font-face` block.

## Deployment

Any push to `master` triggers a Netlify build (no build command — just publishes the root as static files).

## SEO / social

- `<title>`, `<meta name="description">`, `<link rel="canonical">`, Open Graph, and Twitter card are set.
- `og:image` / `twitter:image` are not yet set — add a 1200×630 `og.png` to the repo root, update the `og:image` and `twitter:image` meta tags, and switch `twitter:card` to `summary_large_image`.
