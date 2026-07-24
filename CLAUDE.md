# CLAUDE.md — Tabblie Shopify Theme

This file provides context and working instructions for Claude Code when working on the Tabblie Shopify theme.

---

## Project Overview

**Brand:** Tabblie
**Store:** tabblie.com
**Platform:** Shopify (Online Store 2.0)
**Base theme:** Halo (exported from tabblie.com)
**Purpose:** DTC e-commerce store for eco-friendly household strips (laundry, dishwasher, toilet)

**Store IDs, git setup, CLI commands, GitHub-sync status → `STORE_INFO.md`** (read this before any Shopify CLI or deploy work)
Full brand details → `COMPANY_BRANDING/brand-document.md`
Full website requirements → `COMPANY_BRANDING/PRD.md`
**Live style system (colors, gradients, icons, spacing) → `COMPANY_BRANDING/styling-system.md`**
Market positioning → `COMPANY_BRANDING/market-positioning.md`

---

## Core Mandate — In Priority Order

Every change to this theme must serve these four goals. When a request conflicts with one of them, **say so explicitly — give a recommendation or warning before (or instead of) implementing it as asked.**

1. **Optimized for sales (conversion-first).** This is a DTC e-commerce store; the website exists to sell. Every page should move the visitor toward purchase.
2. **Built the Shopify way.** Online Store 2.0 conventions, JSON templates, section settings, Liquid variables — never fight the platform.
3. **On-brand, always.** Use our brand styling and texts (colors, fonts, logo rules, tone of voice below). If a requested change deviates from the brand — wrong color, off-tone copy, emoji use, dishonest claims — flag it and propose the on-brand alternative.
4. **Fully responsive.** Must look good on every device: phones, tablets, laptops, wide desktops. A change that only works on desktop is not done.

### Conversion / Sales Optimization Rules
- Primary CTA visible above the fold on every page — orange `#E8622A`, high contrast, action-oriented copy
- Product cards always show price and a clear path to buy (one tap/click to PDP or cart)
- Trust signals near every buy decision: reviews/stars, money-back guarantee ("30 dagen proef wassen"), shipping info (NL & BE), payment badges
- Keep friction low: minimal steps to checkout, sticky add-to-cart on PDPs, cart drawer instead of full-page cart
- Use honest urgency/scarcity only — never fake countdown timers or fabricated stock levels
- Subscription upsell ("Abonneer & bespaar 15%") should be present but never block or trick the one-time purchase
- Never bury the product: marketing/mission sections support the sale, they don't replace product visibility
- When making layout/copy decisions, prefer the option that most plausibly increases conversion — and say when a user request is likely to hurt conversion

---

## Brand Identity (Quick Reference)

**Positioning:** Affordable, aesthetic eco-friendly products for everyone — not preachy, not expensive, not ugly.
**Tone:** Cheeky and direct. Never preachy. Never guilt-driven. Family-friendly.
**Tagline:** "Schoonmaken, opnieuw uitgevonden."
**Slogan:** "Tabblie, kind kan de was doen."
**Language:** Dutch (NL) primary. English planned for future.

### Colors
| Token | Hex | Use |
|---|---|---|
| Primary (Orange) | `#E8622A` | Logo, CTAs, brand anchor |
| Background (Warm Cream) | `#FDF6EE` | Page body, cards |
| Text (Dark Earth) | `#1F1209` | Body text, headings |
| Hero Blue | `#E1ECFA` | Homepage hero (gradient to #C8D9F5) |
| Section Pink | `#F8BFD6` | How-it-works, icon strips |
| Wasstrips | `#E8622A` / `#FDEEE6` | Orange accent / card bg |
| Vaatwasstrips | `#F5C842` / `#FDF5DD` | Yellow accent / card bg |
| Toiletstrips | `#5BB8A0` / `#E2F2ED` | Teal accent / card bg |
| Allesreiniger | `#F2A0A0` / `#FCE8E8` | Pink accent / card bg |
| Green (checks) | `#38A169` | Comparison checkmarks, guarantee |
| Blue (verified) | `#3B7DD8` | Verified badges, shipping |
| Trustpilot Green | `#00B67A` | Review stars |

**Color rules:** Orange is brand anchor. Each product has identity color. Sections alternate cream/white/blue/pink/orange. Never use emojis — always SVG icons with varied colors.

### Fonts
**Single typeface across the whole site (updated 2026-07-24): Baloo 2** (Google Fonts, weights 400/500/600/700/800) — chunky rounded face matching the Tabblie wordmark (closest free equivalent of TT Drugs, which is paid). Set via `html:root` overrides in `assets/tabblie-brand.css` for both brand vars (`--heading-font-family`, `--text-font-family`) and the theme-generated vars (`--font-family-1/2`, `--font-heading-family`, `--font-body-family`, menu vars). Fallback: Plus Jakarta Sans.
- Headings: 700 weight, letter-spacing `-0.01em`, line-height `1.1–1.15`
- Body: 400 weight, line-height `1.6–1.7`
- Eyebrows: 600–700, uppercase, letter-spacing `0.1em`, always orange `#E8622A`

### Logo Assets
- **Full wordmark:** Bold orange grotesk "Tabblie" — capital T, rest lowercase (`tabblie-logo.svg` / `tabblie-logo.png`). The wordmark stands alone — **no circle, pill, or badge behind it**.
- **Small logo / Icon:** Orange "T" only (`tabblie-logo-small.png`) — compact UI, mobile sticky nav, app icons
- **Favicon:** 256×256 orange "T" square (`tabblie-favicon.png`)

**Logo rules:** always written "Tabblie" (capital T, rest lowercase) — never "tabblie" all-lowercase, never "TABBLIE" in caps. **This applies to ALL copy everywhere on the site** (headings, body text, FAQs, alt text), not just the logo. Only exception: email addresses (support@tabblie.com). Social handles are also written capitalized in copy (@Tabblie). On light/cream: orange `#E8622A`. On dark/photographic: white. Never stretch, rotate, recolour, or add effects.

> Full style system (colors, gradients, icons, type scale, spacing) → `COMPANY_BRANDING/styling-system.md`

---

## File Structure

```
/assets          → CSS, JS, images, liquid assets (theme files + Tabblie brand assets)
/blocks          → Theme block definitions
/config          → settings_schema.json, settings_data.json (theme settings)
/layout          → theme.liquid (global layout wrapper)
/locales         → Translation files (en.default.json, nl.json etc.)
/sections        → Page sections (.liquid) — main building blocks
/snippets        → Reusable partials called via {% render %}
/templates       → Page templates (JSON-based for OS2.0)
/docs            → Brand document, PRD (not Shopify files — reference only)
```

> Note: Theme files live at the **repo root** so Shopify's GitHub integration can detect them directly.

---

## Working Principles

### Keep documentation in sync
When a change alters anything these docs describe (fonts, colors, claim language, tone, URLs, workflow), update the relevant MD files in the same session: this file, `STORE_INFO.md`, `COMPANY_BRANDING/CLAUDE.md`, `COMPANY_BRANDING/styling-system.md`. Docs must never contradict the live site. In doubt whether something is a new standard or a one-off experiment? **Ask before documenting it.**

### Always follow the brand
- Use `#E8622A` for all primary CTAs and highlights — no grey or muted buttons
- Background color for most sections: `#FDF6EE` (warm cream), not pure `#FFFFFF`
- Copy tone must be cheeky and direct — avoid corporate/generic language
- Never use dark green as a brand color — it reads as "typical eco brand"
- **Claim language (updated 2026-07-24):** **"100% plasticvrij"** (NL) / "plastic-free" (EN) is the approved claim — the strips use a seaweed-based carrier (no PVA/microplastics) and paper packaging. "Geen plasticafval" is also fine but "100% plasticvrij" is preferred. Do not walk claims back to the old "geen plasticafval"-only wording.

### Shopify-specific rules
- This is an **Online Store 2.0** theme — sections are JSON-defined in `/templates`
- Edit section settings via `sections/*.liquid` files
- Global theme settings live in `config/settings_schema.json` (schema) and `config/settings_data.json` (values)
- Liquid variables use `{{ }}` for output, `{% %}` for logic
- Use `{% render 'snippet-name' %}` to include snippets — not `{% include %}`
- Always use `| escape` on user-generated content to prevent XSS

### Responsive Design — Non-Negotiable
Every change must work perfectly on **both mobile and desktop**. This is a core requirement, not an afterthought.
- **VERIFY EVERY CHANGE ON MOBILE BEFORE CALLING IT DONE.** Any visual/layout change must be checked at mobile width (390px) AND desktop width — use browser screenshots (Playwright against the `shopify theme dev` preview) when available. A change that only looks right on desktop is a bug, not a finished task. Never propose a commit for visual work that hasn't had its mobile check.
- Watch for desktop-tuned values leaking to mobile: absolute/percentage positioning, fixed widths, large paddings, and section-relative offsets often need their own mobile values
- **Mobile-first always** — write CSS starting from the smallest screen and scale up with `min-width` breakpoints
- Test all layouts at: 375px (iPhone SE), 390px (iPhone 14), 768px (iPad), 1280px (desktop), 1440px (wide)
- Touch targets must be at least 44×44px — buttons, links, nav items
- No horizontal scroll on any viewport — every layout must fit within its container
- Stacked layouts on mobile, side-by-side on desktop — never force desktop patterns onto small screens
- Font sizes: minimum 16px body on mobile (prevents iOS zoom on input focus)
- Hero sections: full-width on mobile, reduced padding — never crop important content
- Images must use responsive `srcset` / Shopify's `| image_url: width:` filters — never fixed pixel widths
- Navigation: hamburger menu on mobile, full nav on desktop — always sticky on scroll

### SEO — Built In From the Start
Every page and section must be SEO-ready by default.
- All sections that render headings must use semantically correct heading hierarchy (`h1` → `h2` → `h3`) — never skip levels
- Every page has exactly **one `<h1>`** — never zero, never more than one
- Product and collection pages: use `page_title` and `page_description` Liquid variables for `<title>` and `<meta name="description">`
- All images must have descriptive `alt` attributes — use product/section names, never empty alt on meaningful images
- Use `{{ canonical_url }}` — already in `theme.liquid`, never remove it
- Structured data (JSON-LD): add `Product`, `BreadcrumbList`, and `Organization` schema where appropriate
- Internal links must use descriptive anchor text — never "click here"
- Avoid duplicate content: use `?sort_by` / `?page=` canonical tags correctly (Shopify handles this natively)
- Meta titles: `{{ page_title }} – tabblie` format, under 60 characters
- Meta descriptions: under 155 characters, include a clear value proposition

### Performance — Core Web Vitals Green
Every change must protect or improve page speed. Target: Core Web Vitals green on mobile.
- **No render-blocking resources in `<head>`** — all scripts use `defer` or are loaded in footer
- Stylesheets for non-critical components: use `media="print" onload="this.media='all'"` pattern (already used in `global-style.liquid`)
- Images: always use Shopify's image CDN (`| image_url: width: 800`) — never hotlink external images
- Use `loading="lazy"` on all images below the fold — `loading="eager"` only on the hero/LCP image
- Use `fetchpriority="high"` on the hero image (LCP element) to improve LCP score
- Avoid large layout shifts — always set explicit `width` and `height` (or aspect-ratio) on images and media
- No third-party scripts loaded synchronously — always async/defer
- Inline only truly critical CSS (above-the-fold styles) — keep it minimal
- Prefer CSS animations over JS animations for simple effects
- Fonts: use `font-display: swap` — Google Fonts already handles this; don't override it
- Minimize Liquid logic in loops — avoid complex nested loops inside `for` blocks in sections

### CSS / Styling
- Theme uses CSS custom properties (variables) — check `snippets/variable.liquid` before hardcoding values
- Prefer editing/extending existing CSS in `assets/base.css` or adding to `assets/custom.css` over inline styles
- Mobile-first: all new styles start mobile and use `min-width` breakpoints

### Translations
- All user-facing strings must have translation keys in `locales/en.default.json` and `locales/nl.json`
- Use `{{ 'key' | t }}` in Liquid for translated strings
- Never hardcode English-only text in section/snippet files

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

Refer to `COMPANY_BRANDING/PRD.md` for full scope.

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
