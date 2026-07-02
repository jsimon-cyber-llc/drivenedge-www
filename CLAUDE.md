# Driven Edge — Website (`drivenedge.net`)

Public marketing site for **Driven Edge**. Static, dependency-free; the published
site lives in `site/` and deploys to **GitHub Pages** via
`.github/workflows/deploy-pages.yml` on every push to `main`. Live at
https://drivenedge.net.

> This file is auto-loaded context for any session opened in this repo. Operational
> details (DNS/hosting tokens, image-generation credentials, the Cloudflare account)
> are intentionally **not** in this public repo — they live in the maintainer's
> private notes. One standing item there: **rotate the Cloudflare API token** that
> was exposed during setup.

## Positioning — keep general (do NOT regress)
- Driven Edge is a **technology & AI consultancy** (IT + AI consulting). Kept general.
- **AI is front-and-center**: AI strategy, **AI integration into existing systems &
  workflows**, **AI-as-a-service & agents**, plus software engineering, data/platforms,
  reliability/security/governance.
- **Product-agnostic**: never name a specific product, market, or client.
- **Never self-limit**: no geography / "based in" / jurisdiction, and no size words
  ("studio", "software studio", "small studio/team/company"). The only "LLC" allowed is
  the tiny footer copyright + the JSON-LD `legalName`.
- **Audience is B2B / enterprise** (we serve organizations, not consumers) — but **never
  write the word "B2B" or "business-to-business" on the site**; it's jargon. Address the
  buyer *implicitly*: "organizations", "your teams", "the systems you run", "enterprises".
- **Honest**: invent no clients, metrics, headcount, awards, or scale.

## Voice
- Executive / enterprise-consulting register (think Deloitte / Accenture / Leidos / GDIT):
  confident, understated, precise. No emoji, no hype.
- Avoid the "AI-written" cadence: **minimize em-dashes**, avoid rule-of-three lists and
  balanced/parallel clauses, vary sentence rhythm, add specificity and a real point of view.
- Headline "We build software worth keeping." is kept.

## Design system — "Precision Instrument"
- Palette: warm graphite neutrals + a single **rationed Edge-Amber `#C2410C`** accent
  (its own identity, deliberately off the blue/emerald other products use). Tokens in
  `site/assets/tokens.css`; components in `site/assets/styles.css`.
- Fonts: **Fraunces** (display/serif headlines), **Inter** (body), **JetBrains Mono**
  (labels/chrome).
- Signature devices: amber **registration-mark reticle corners** + a **measurement ruler**.
- Numbered **sections** (01–05) are fine. **Do NOT** add fake per-item "spec codes"
  (`C-01`, `P-01`, `L1`, `DE·00`) or decorative amber pips on eyebrows — they read as
  AI-template filler.

## Imagery & diagrams
- **One** real photographic hero only: `site/assets/img/hero.jpg` (machined-metal macro).
  Don't reuse the hero image anywhere else on the page.
- Diagrams are **hand-built inline SVG** with the real fonts, in an engineering-drawing
  style (faint grid, reticles, corner ticks) — never generic SaaS card grids, never
  AI-raster (which garbles text). "How we build" = reference architecture (uses a second,
  distinct real image `site/assets/img/ai-layer.jpg`); "How we work" = engagement model.
- New visual assets: prefer hand-built vector for anything with text; photoreal images via
  the maintainer's Vertex image kit (private). Always visually QA the exact artifact.

## Structure, build & deploy
- `site/` is the web root: `index.html`, `privacy.html`, `terms.html`, `CNAME`
  (`drivenedge.net`), `robots.txt`, `sitemap.xml`, `site.webmanifest`, `assets/`.
- Local preview: `cd site && python3 -m http.server 8911`.
- Deploy: commit + push to `main` → the Pages workflow publishes `site/`. **GitHub is the
  source of truth — commit and push promptly; never leave work only local.** Verify the
  change is actually live at https://drivenedge.net before calling it done.

## Accessibility & progressive enhancement (do not regress)
- All content must be visible **without JavaScript** (the scroll-reveal is gated behind an
  `html.js` class). Keep skip link, semantic landmarks, visible focus, AA+ contrast, and
  `prefers-reduced-motion` support.

## Legal pages
- `privacy.html` / `terms.html` must always resolve (they're linked in the footer). Privacy
  is intentionally **general/broad** (discretionary handling within Driven Edge's control);
  terms' governing-law clause is neutralized to "applicable law".
