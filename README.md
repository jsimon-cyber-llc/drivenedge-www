# Driven Edge — Company Website (`drivenedge.net`)

The public website for **Driven Edge LLC** — a United States technology company
that designs and builds digital products and the tools behind them.

> This repository contains **only the company marketing website**. It is a single,
> production-grade, dependency-free static page (plus minimal Privacy and Terms pages).
> It intentionally stays **general** — it describes who the company is and how it
> works, not any specific product.

---

## What this is

- **Hand-written** `HTML` + `CSS` + a small vanilla-JS interactions module — no framework, no build step.
- **Light editorial design system** in a warm graphite-and-amber palette. Neutrals do ~90% of the
  work; the single **Edge-Amber** accent (`#C2410C`) is rationed to CTAs, links, focus, and one
  emphasized word. Fraunces (display), Inter (body), JetBrains Mono (labels/detail).
- **Progressive-enhancement first.** All content is visible without JavaScript; the scroll-reveal
  animation is gated behind an `html.js` class and only activates when JS is present.
- **Complete machine-readable `<head>`**: canonical, Open Graph + Twitter cards, `Organization`
  JSON-LD, theme-color, favicon set, web manifest, robots + sitemap.
- **Accessibility**: skip link, semantic landmarks, visible focus, AA+ contrast, `prefers-reduced-motion`.

## Structure

```
site/                      # ← the published site root (served at drivenedge.net/)
  index.html               # the one-page site
  privacy.html             # privacy policy
  terms.html               # terms of use
  favicon.svg              # the "D / forged-edge" logomark
  apple-touch-icon.png     # 180×180 (opaque, full-bleed)
  site.webmanifest
  og.jpg                   # 1200×630 social card
  CNAME                    # custom domain (drivenedge.net)
  robots.txt
  sitemap.xml
  assets/
    tokens.css             # design tokens (color, type scale, spacing, radius, elevation)
    styles.css             # component + layout styles
    main.js                # footer year, mobile nav, scroll reveal
    og.html                # source for the social-share card
    icons/                 # 32 / 192 / 512 / 512-maskable PNGs
.github/workflows/
    deploy-pages.yml        # deploys ./site to GitHub Pages on push to main
```

## Local preview

No build step. Serve the `site/` folder over HTTP (absolute `/assets/...` paths need a server):

```bash
cd site && python3 -m http.server 8911
# open http://localhost:8911
```

## Deploy

Publishes the `site/` folder to **GitHub Pages** via GitHub Actions
(`.github/workflows/deploy-pages.yml`) on every push to `main`. To go live on `drivenedge.net`:

1. In repo **Settings → Pages**, set **Source: GitHub Actions** (one-time).
2. Point DNS for the apex `drivenedge.net` at GitHub Pages (`A`/`AAAA` records to GitHub's
   Pages IPs) and add a `www` `CNAME` → `jsimon-cyber-llc.github.io`. The `site/CNAME` file
   already declares the domain.
3. Push to `main`; the workflow builds and deploys.

## Brand / content guardrails (do not regress)

- **Stay general.** Never name a specific product, market, or vertical on this site.
- **Amber is rationed**, never decorative — CTAs, links, focus, and one emphasized word only.
- **Icons/marks only, never emoji.**
- **Content must render without JavaScript** — keep the `html.js` gating on `[data-reveal]`.
- **Keep the legal pages real** — `/privacy.html` and `/terms.html` must always resolve.

---

© Driven Edge LLC · A United States software company.
