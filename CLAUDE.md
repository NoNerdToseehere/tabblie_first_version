# CLAUDE.md — Tabblie Shopify Theme

This file provides context and working instructions for Claude Code when working on the Tabblie Shopify theme.

---

## Project Overview

**Brand:** Tabblie
**Store:** usetabbly.com
**Platform:** Shopify (Online Store 2.0)
**Base theme:** Impact
**Purpose:** DTC e-commerce store for eco-friendly household strips (laundry, dishwasher, toilet)

Full brand details → `docs/brand-document.md`
Full website requirements → `docs/PRD.md`

---

## Brand Identity (Quick Reference)

**Positioning:** Affordable, aesthetic eco-friendly products for everyone — not preachy, not expensive, not ugly.
**Tone:** Cheeky and direct (like Fussy deodorant). Never preachy. Never guilt-driven.
**Tagline:** "Clean our world."
**Language:** English (default) + Dutch (NL)

### Colors
| Token | Hex | Use |
|---|---|---|
| Primary (Orange) | `#E8622A` | Logo, CTAs, brand elements — on every product and page |
| Background | `#FDF6EE` | Page backgrounds, cards |
| Text | `#1F1209` | Body text, headings |
| Product: All-Purpose | `#E8622A` | Orange — same as primary |
| Product: Kitchen | `#F5C842` | Sunny Yellow |
| Product: Bathroom | `#5BB8A0` | Soft Teal |
| Product: Hand Soap | `#F2A0A0` | Blush Pink |

**Color rule:** Orange is always the brand anchor on every product (logo, typography, icons). Each product additionally has its own identity color for label/accent — like the kraft packaging uses orange on a neutral base.

### Fonts
- **Headings:** Fraunces (expressive serif)
- **Body:** DM Sans (clean sans-serif)
- **Logo:** Always lowercase — `tabblie` — never capitalised

---

## File Structure

```
/assets          → CSS, JS, images, liquid assets
/config          → settings_schema.json, settings_data.json (theme settings)
/layout          → theme.liquid (global layout wrapper)
/locales         → Translation files (en.default.json, nl.json etc.)
/sections        → Page sections (.liquid) — main building blocks
/snippets        → Reusable partials called via {% render %}
/templates       → Page templates (JSON-based for OS2.0)
/docs            → Brand document, PRD (not Shopify files — reference only)
```

---

## Working Principles

### Always follow the brand
- Use `#E8622A` for all primary CTAs and highlights — no grey or muted buttons
- Background color for most sections: `#FDF6EE` (warm cream), not pure `#FFFFFF`
- Copy tone must be cheeky and direct — avoid corporate/generic language
- Never use dark green as a brand color — it reads as "typical eco brand"

### Shopify-specific rules
- This is an **Online Store 2.0** theme — sections are JSON-defined in `/templates`
- Edit section settings via `sections/*.liquid` files
- Global theme settings live in `config/settings_schema.json` (schema) and `config/settings_data.json` (values)
- Liquid variables use `{{ }}` for output, `{% %}` for logic
- Use `{% render 'snippet-name' %}` to include snippets — not `{% include %}`
- Always use `| escape` on user-generated content to prevent XSS

### CSS / Styling
- Theme uses CSS custom properties (variables) — check `snippets/css-variables.liquid` before hardcoding values
- Prefer editing/extending existing CSS in `assets/theme.css` over adding inline styles
- Mobile-first: all new styles should start mobile and use `min-width` breakpoints

### Translations
- All user-facing strings must have translation keys in `locales/en.default.json` and `locales/nl.json`
- Use `{{ 'key' | t }}` in Liquid for translated strings
- Never hardcode English-only text in section/snippet files

### Performance
- Do not add blocking scripts to `<head>` — use `defer` or load in footer
- Prefer SVG for icons (already used throughout theme)
- Compress any new images before adding to `/assets`

---

## Key Files to Know

| File | Purpose |
|---|---|
| `layout/theme.liquid` | Global HTML wrapper — header, footer, scripts |
| `sections/header.liquid` | Site header + navigation |
| `sections/footer.liquid` | Site footer |
| `snippets/css-variables.liquid` | All CSS custom property definitions |
| `snippets/product-card.liquid` | Reusable product card component |
| `snippets/price-list.liquid` | Price display logic (one-time + subscription) |
| `config/settings_schema.json` | Theme settings UI definitions |
| `config/settings_data.json` | Current theme settings values |
| `locales/en.default.json` | English translations |

---

## What We're Building

Refer to `docs/PRD.md` for full scope.

### Phase 1 — Strips (Launch)
1. Apply Tabblie brand colors and fonts throughout the theme
2. Homepage: hero ("Clean our world."), product grid, mission strip, how-it-works, initiative teaser, reviews, email capture
3. Product pages: one-time + subscription toggle, benefit icons, how-to-use section
4. Environmental Initiative page (10% of profits commitment)
5. Bilingual: EN + NL throughout
6. Cart drawer with subscription upsell nudge

### Phase 2 — Tablets + Glass Bottles
7. 4 cleaning tablet products, each with identity color on their PDP
8. Starter Kit bundle page (glass bottle + tablet refills)
9. Collection page filterable by product type

---

## Do Not

- Do not remove or break existing Shopify section schema blocks — always extend, don't replace
- Do not hardcode prices or product handles — always use Liquid variables
- Do not commit `config/settings_data.json` changes unless intentional — it contains live store settings
- Do not add new npm/build dependencies — this is a standard Shopify theme with no build pipeline
- Do not use pure black (`#000000`) or pure white (`#FFFFFF`) as primary brand colors
- Do not add eco clichés: no green leaves, no hands holding globes, no "save the planet" guilt copy
