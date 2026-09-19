# Rootz + Rituals

Marketing site for Rootz + Rituals — rootwork, spelled products, energy
services, tarot and astrology. Black and antique-gold branding, preserved
from the original single-file design and split into a small static project
so it's easy to keep developing.

## Getting started

```bash
npm install
npm run dev
```

Visit the URL Vite prints (usually `http://localhost:5173`).

Other scripts:

```bash
npm run build      # production build into dist/
npm run preview    # preview the production build locally
```

## Project structure

```
index.html         Page markup — all sections, nav, and copy
src/style.css       All styling (colors, layout, responsive rules)
```

This is a static site — no framework, no build-time content pipeline. Every
section lives directly in `index.html`; every visual rule lives in
`src/style.css`. Vite is used only as a local dev server with hot reload and
to produce an optimized `dist/` build for deployment.

## Sections in `index.html`

- `.nav` — sticky header, nav links, "Book a reading" button
- `#top .hero` — hero headline, sigil illustration, primary CTAs
- `.ticker` — scrolling ingredient/keyword strip
- `#offerings` — the three "doorways" (Rootwork / Spelled products / Energy services)
- `#ritual` — "The Rootz + Rituals way" altar illustration + copy + pillars
- `#products` — the product collection grid (8 items)
- `#guidance` — the two reading/booking cards
- `.final` — closing call-to-action band
- `footer` — footer nav + copyright

## Editing content

- **Products**: edit or add `<article class="product">` blocks inside
  `#products .products`. Each has an icon glyph (`.mark`), a name, a short
  description, and a category label (`<small>`).
- **Copy/headlines**: edit directly in the relevant section in `index.html`.
- **Links that repeat across the page** — update these in every place they
  appear (search the file for the URL):
  - Instagram: `https://www.instagram.com/rootz_rituals/`
  - Booking (Cal.com): `https://cal.com/samira-jackson-bhwepq`
- **Colors/branding**: CSS variables at the top of `src/style.css`
  (`--ink`, `--gold`, `--gold2`, `--cream`, `--muted`, `--line`).

## Navigation & external links

All in-page nav links (`#offerings`, `#products`, `#ritual`, `#guidance`,
`#top`) point at section `id`s that exist in `index.html`, so they work as
soon as the page loads — no JS required. External links (Instagram, Cal.com)
open in a new tab (`target="_blank" rel="noreferrer"`).

## Deploying to Vercel

1. Push this repo to GitHub (already done if you're reading this from the
   repo).
2. In Vercel, **Add New Project** → import this GitHub repo.
3. Framework preset: **Vite** (auto-detected). Build command `npm run
   build`, output directory `dist` (Vercel fills these in automatically).
4. Deploy.

### Connecting your domain

1. In the Vercel project, go to **Settings → Domains** and add your Rootz +
   Rituals domain.
2. Vercel will show either an A record + value or nameservers to set,
   depending on where the domain is registered. Add those records at your
   domain registrar (or switch nameservers to Vercel's, if you choose that
   route).
3. Wait for DNS to propagate (usually minutes, sometimes longer) — Vercel's
   Domains page shows verification status live and issues an SSL
   certificate automatically once it verifies.

## Continuing development with Claude

This project has no backend, no build-time content system, and no
dependencies beyond Vite — so Claude (or any editor) can work directly in
`index.html` and `src/style.css` without needing to understand a framework
first. Good next steps if you want to grow this:

- Wire the product grid up to a real store (Shopify, a headless CMS, etc.)
  when you're ready to sell online.
- Replace the CSS-only `.sigil` / `.altar` illustrations with real
  photography or artwork.
- Add a contact form or newsletter signup.
