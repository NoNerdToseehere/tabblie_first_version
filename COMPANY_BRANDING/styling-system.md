# Tabblie — Live Styling System
*The operational source of truth for colors, type, icons, and spacing as implemented on the live Tabblie theme.*
*Last audited: 2026-04-15*

> This document mirrors what is actually in the code. If you change a pattern in the theme, update this file too. For brand philosophy and tone see `brand-document.md`. For product scope see `PRD.md`.

---

## 1. Color Palette — Live Values

### Brand anchors (every page uses these)

| Token | Hex | Where |
|---|---|---|
| Tabblie Orange | `#E8622A` | Logo wordmark, CTAs, eyebrows, active states, link hover, icon tints |
| Warm Cream | `#FDF6EE` | Page body background, card backgrounds, alternate section rhythm |
| Pure White | `#FFFFFF` | Alternate section rhythm — content-heavy blocks (testimonials, ingredients, education, FAQ) |
| Deep Earth (text) | `#1F1209` | All body copy and headings |
| Deep Earth 70% | `rgba(31, 18, 9, 0.7)` | Secondary body copy |
| Deep Earth 65% | `rgba(31, 18, 9, 0.65)` | Paragraph body in hero blocks |
| Deep Earth 50% | `rgba(31, 18, 9, 0.5)` | Subtitles, captions |
| Deep Earth 10% | `rgba(31, 18, 9, 0.1)` | Card borders, FAQ dividers |
| Deep Earth 8% | `rgba(31, 18, 9, 0.08)` | USP-strip bottom border, subtle dividers |
| Deep Earth 6% | `rgba(31, 18, 9, 0.06)` | Comparison table rows, lightest shadows |

### Section accent colors (beyond orange)

| Name | Hex | Where used |
|---|---|---|
| Soft Teal | `#5BB8A0` | USP icons (leaf, shield, recycle), decorative leaves, eco badges |
| Sunny Yellow | `#F5C842` | Star ratings, decorative leaves (highlight), vaatwasstrips identity |
| Coral Pink | `#E85B7A` | "Heart / vegan" USP icon |
| Trust Blue | `#3B7DD8` | "Verified", truck, check USP icons |
| Checkmark Green | `#38A169` | Comparison table checkmarks, guarantee cues |
| Trustpilot Green | `#00B67A` | Review star block on PDP |
| Blush Pink (product) | `#F2A0A0` | Allesreiniger identity |
| Hero Blue light | `#E1ECFA` | Collection hero gradient start |
| Hero Blue mid | `#C8D9F5` | Collection hero gradient middle |
| Section Pink (HIW bg) | `#F8BFD6` | How-it-works background |
| Off-white eco | `#F0F7EE` | Carbon-offset section background |

### Product identity pairs (accent + card-bg)

| Product | Accent | Card background |
|---|---|---|
| Wasstrips | `#E8622A` | `#FDEEE6` |
| Vaatwasstrips | `#F5C842` | `#FDF5DD` |
| Toiletstrips | `#5BB8A0` | `#E2F2ED` |
| Allesreiniger | `#F2A0A0` | `#FCE8E8` |

### Gradients (exact CSS)

```css
/* Newsletter splash (footer + homepage) */
background: linear-gradient(135deg, #E8622A 0%, #F5934A 100%);

/* Collection hero background */
background: linear-gradient(160deg, #E1ECFA 0%, #C8D9F5 40%, #D5E3F8 70%, #E8EFF9 100%);

/* Product feature placeholder */
background: linear-gradient(135deg, rgba(232,98,42,0.12) 0%, rgba(243,226,206,0.6) 100%);

/* Product image frame (PDP) — gradient border via padding */
background: linear-gradient(135deg, #E8622A 0%, #F5C842 50%, #5BB8A0 100%);
```

### Section background map (which section → which color)

| Section | Background |
|---|---|
| tabblie-page-hero (default) | `#FDF6EE` |
| tabblie-collection-hero | Blue gradient (above) |
| tabblie-product-feature | `#FFFFFF` |
| tabblie-product-cards | `#FDF6EE` — three product tiles in their identity pastels; the `tabblie-coming-soon` blue canvas tucks under it at the same 1100px width when it follows directly (2026-09-02) |
| tabblie-testimonials | `#FFFFFF` |
| tabblie-ingredients | `#FFFFFF` |
| tabblie-education | `#FFFFFF` |
| tabblie-faq | `#FFFFFF` |
| tabblie-guarantee | `#FDF6EE` |
| tabblie-comparison | `#FDF6EE` |
| tabblie-founder | `#FDF6EE` |
| tabblie-how-it-works | `#F8BFD6` |
| tabblie-how-it-works-v2 | Pink splash gradient w/ "1 2 3" watermark |
| tabblie-carbon-offset | `#F0F7EE` |
| tabblie-impact | `#E8622A` (white text) |
| tabblie-newsletter | Orange gradient (above) |

**Rhythm rule:** alternate cream → white → cream → white down the page, with orange (`tabblie-impact`) or blue (collection hero) as high-impact breakpoints. Avoid two identical backgrounds in a row.

---

## 2. Typography (updated 2026-07-24)

### Single typeface
**Baloo 2** — Google Fonts, weights 400/500/600/700/800. Chunky rounded face matching the Tabblie wordmark (closest free equivalent of TT Drugs, which is a paid font). Fallback: Plus Jakarta Sans. Used for *everything*: headings, body, buttons, menus, footer.

**⚠️ Baloo 2 has NO italics.** Never use `font-style: italic` — the browser synthesizes a thin slanted fake that reads as a wrong font. Accents that used to be italic are now **weight 800, normal style, orange**.

### Where it's implemented (all three layers must stay in sync)
1. **Theme settings** (`config/settings_data.json`): `type_font_1_name` / `type_font_2_name` = `"Baloo 2"` — feeds all settings-driven components (product card titles etc.)
2. **`assets/tabblie-brand.css`** `html:root` block: overrides both brand vars (`--heading-font-family`, `--text-font-family`) and every theme-generated var (`--font-family-1/2`, `--font-heading-family`, `--font-body-family`, menu/mega-menu/btn/footer/page-title vars)
3. **`snippets/global-style.liquid`**: Google Fonts load, weights 400–800, `display=swap`

### CSS variables
```css
--heading-font-weight: 700;
--text-font-weight: 400;
--heading-letter-spacing: -0.01em;
--text-letter-spacing: 0em;
```

### Weights — the system
| Element | Weight |
|---|---|
| All headings h1–h3 + tabblie section titles | **700** (forced via global rule in tabblie-brand.css — Baloo at 400 reads like a different, thin font) |
| Orange heading accents ("opnieuw uitgevonden.", "Risicovrij!", "Tabblie" in comparison) | **800**, `font-style: normal`, `#E8622A` |
| PDP product title (h1.productView-title) | **800**, `clamp(30px, 3.2vw, 42px)` (28px mobile), line-height 1.12 |
| Product card titles (a.card-title) | **700** |
| Eyebrows (uppercase labels) | **600** (700 gets blobby at 13px) |
| Body | **400** |

### Type scale (live `clamp()` values)

| Element | CSS |
|---|---|
| Page hero H1 | `clamp(2.8rem, 6vw, 5.2rem)` |
| Section H2 | `clamp(2.2rem, 4vw, 3.4rem)` |
| PDP product title | `clamp(30px, 3.2vw, 42px)` |
| Newsletter heading | `clamp(2.6rem, 5vw, 4rem)` |
| Discount display | `clamp(4rem, 8vw, 6.5rem)` |
| Card H3 | `clamp(1.25rem, 2vw, 1.5rem)` |
| Body | `14–16px` (16px min on mobile) |
| Eyebrow | `13px` fixed, uppercase |
| Small / caption | `11–15px` |

### Line heights
- Headings: `1.1` – `1.15`
- Body: `1.6` – `1.7`
- Eyebrows: `1.5`

### Rules
- Eyebrows always orange `#E8622A`, weight 600, letter-spacing `0.1em`, uppercase
- Never `font-style: italic` anywhere (Baloo 2 has no italics — see above)
- Never drop below 400 weight (accessibility)
- Body text minimum 16px on mobile to avoid iOS zoom on inputs
- **"Tabblie" is always capitalized** in every piece of copy (headings, body, FAQs, alt text, social: @Tabblie, Tabblie.com). Only exception: email addresses (support@tabblie.com)

---

## 3. Icons

### SVG icon inventory (used across tabblie-*.liquid)

| Icon | Purpose | Color | Sections |
|---|---|---|---|
| Check (thin stroke) | Benefit bullet | `#E8622A` | product-feature |
| Check (thick) | Comparison ✓ | `#38A169` | comparison |
| X-mark | Comparison ✗ | `rgba(31,18,9,0.35)` | comparison |
| Arrow right | CTA glyph | `#E8622A` | product-feature, ingredients |
| Plus / minus | FAQ toggle (CSS ::before/::after bars, 16×2 / 2×16 px) | `#E8622A` | faq |
| Leaf | Eco | `#5BB8A0` | usp-strip, decorative leaves |
| Heart | Vegan/love | `#E85B7A` | usp-strip |
| Truck | Shipping | `#3B7DD8` | usp-strip |
| Shield | Trust/safe | `#5BB8A0` | usp-strip |
| Recycle | Sustainability | `#5BB8A0` | usp-strip |
| Star (polygon) | Rating | `#F5C842` | usp-strip |
| Star (flat SVG, 19px — the `tabblie-review-score` shape) | Review rating | `#E8622A` | PDP score, product rows, testimonials |
| Check-circle | NL flag substitute → replaced by tricolor band | — | usp-strip |
| Globe | World/mission | `#E8622A` | faq (section icon) |
| Turtle | Vegan/animal | `#E8622A` | faq (section icon) |
| Question mark | FAQ section mark (stroke path + rounded-cap line dot) | `#E8622A` | faq |
| Box / shipping / return / leaf | FAQ section icon options | `#E8622A` | faq |
| Decorative leaf (organic path) | Ambient background | Teal/Orange/Yellow @ 0.08–0.18 opacity | testimonials, guarantee, ingredients, founder, comparison — desktop only |
| How-it-works ring ellipse | Badge frame | white stroke, 2.5px | how-it-works |

### Image-based icons

| Asset | Purpose | Size shown |
|---|---|---|
| `tabblie-carbon-footprint.png` | Green footprint badge | 90×90px desktop, 64×64px mobile (section) / 18×18px inline (USP) |
| `tabblie-plasticfree.png` | Circular green eco badge, 22×22px inline (USP strip, announcement bar). ⚠️ **Current asset reads "100% PLASTIC FREE" — must be regenerated to say "NO PLASTIC WASTE" to match honest-claim messaging.** | 22×22px inline |
| `stars-4.7.svg` | Trustpilot 4.7 stars | dynamic, PDP |

### Payment icons (`/assets/pay-*.svg` + `.png`)
`pay-ideal.svg`, `pay-visa.svg`, `pay-master.svg`, `pay-applepay.svg`, `pay-paypal.svg`, `pay-klarna.png` — rendered in a single row on PDP checkout area.

### Logo assets

| File | Purpose |
|---|---|
| `tabblie-logo.svg` / `tabblie-logo.png` | Full orange bold wordmark (header, footer) |
| `tabblie-logo-dark.svg` | Dark variant (on light photographic backgrounds if needed) |
| `tabblie-logo-small.png` | Orange "T" only — compact UI, mobile sticky nav, social avatars |
| `tabblie-favicon.png` | 256×256 — orange script "T" on hero blue with a soap bubble, browser tab |
| `tabblie-favicon-48/96/144/180/192.png` | Sized variants — Google only accepts favicons that are a multiple of 48px |

**Never:**
- Use emojis anywhere on the site
- Recolor icons outside the palette above
- Wrap the wordmark in a circle, pill, or badge

---

## 4. Buttons & CTAs

### Primary CTA (solid orange pill) — THE button standard (updated 2026-07-26)
Every buy/CTA button on every page is a SOLID orange pill with BOLD white text.
Outline/ghost buttons are off-brand for primary actions.
```css
background: #E8622A;         /* solid — never transparent, never grey */
color: #FFFFFF;              /* white, ALSO on hover (guard against theme a:hover) */
padding: 15–17px 32–36px;    /* big CTAs: 17px 36px */
border-radius: 100px;
font-size: 15–18px;          /* hero/PDP CTAs: 18px */
font-weight: 800;            /* bold is the brand — 600 reads too thin in Baloo 2 */
border: none;
transition: background 0.2s ease;

/* hover */
background: #cf531e;
color: #FFFFFF;              /* explicitly re-set; theme a:hover turns it orange */
```

### Secondary CTA (orange outline pill)
```css
background: transparent;
color: #E8622A;
border: 1.5px solid #E8622A;
padding: 14px 28px;
border-radius: 100px;
font-size: 15px;
font-weight: 600;
transition: background 0.2s ease, transform 0.2s ease;

/* hover */
background: #E8622A;
color: #FDF6EE;
transform: translateY(-1px);
```

### Newsletter CTA (white on gradient)
```css
background: #FFFFFF;
color: #E8622A;
padding: 10px 24px;   /* mobile: 12px */
border-radius: 100px;
font-size: 14px;
font-weight: 700;

/* hover */
background: #FDF6EE;
transform: scale(1.03);
```

### With trailing icon
- gap `8px` between text and 16×16 SVG arrow
- hover icon `transform: translateX(3px)`

---

## 5. Border Radii

| Value | Use |
|---|---|
| `100px` | Pill buttons, newsletter input, announcement-bar badges |
| `50%` | Circular avatars, guarantee badge, icon circles |
| `20px` | Large image containers (founder portrait, guarantee visual), testimonial sticker cards |
| `16px` | Cards, ingredient tiles, comparison table |
| `12px` | Form inputs, smaller cards |
| `8px` | Tight UI chips |
| `2px` | Divider bars, FAQ toggle bars |
| `0` | Tables, raw grid cells |

---

## 6. Shadows

| Purpose | CSS |
|---|---|
| Product/feature card (rest) | `0 8px 24px rgba(232, 98, 42, 0.12)` |
| Card hover | `0 4px 16px rgba(232, 98, 42, 0.20)` |
| High-emphasis badge (guarantee 30-day circle) | `0 4px 20px rgba(232, 98, 42, 0.30)` |
| Newsletter / footer buttons | `0 6px 20px rgba(232, 98, 42, 0.15)` |
| Subtle dark card | `0 2px 16px rgba(31, 18, 9, 0.06)` |
| Subtle dark card (mobile) | `0 2px 12px rgba(31, 18, 9, 0.06)` |
| White ring (HIW badges) | `box-shadow: 0 0 0 3px #FFFFFF` |

**Rule:** shadows are warm orange-tinted (preferred) or low-opacity dark earth. Never pure black.

---

## 7. Spacing & Layout

### Section vertical padding

| Scale | CSS | Used in |
|---|---|---|
| Large | `clamp(56px, 7vw, 96px)` | product-feature, testimonials, ingredients, education, FAQ, founder |
| Medium | `clamp(48px, 6vw, 80px)` | stats, how-it-works, comparison, guarantee |
| Small | `clamp(36px, 4vw, 56px)` | impact, carbon-offset, education header |
| Minimal | `10px` | USP strip, deal bar |

### Horizontal gutters
- Desktop: `clamp(16px, 3vw, 40px)`
- Mobile (≤749px): `20–24px` hardcoded

### Max widths

| px | Use |
|---|---|
| 1200 | Ingredient grid container |
| 1100 | Most section inner wrappers |
| 860  | Carbon-offset |
| 800  | Comparison table |
| 780  | Page hero, stats header |
| 720  | Impact |
| 900  | Testimonial carousel card (`--testi-card-w`, ~1.66:1 like the reference, neighbours peek in the gutters) |
| 620  | Newsletter |
| 560  | Body copy blocks under headings |

### Grid gaps

| Gap | Use |
|---|---|
| `clamp(36px, 5vw, 64px)` | Two-column layouts |
| `clamp(32px, 4vw, 56px)` | Header → content spacing |
| `clamp(24px, 3vw, 48px)` | 3-col grids |
| `clamp(20px, 2.5vw, 36px)` | Card padding |
| `clamp(16px, 2vw, 24px)` | Tight grids |
| `8–12px` | Inline (icon + text) |

### Breakpoints
- Mobile: `≤749px`
- Tablet: `750–1023px`
- Desktop: `≥1024px`

---

## 8. Animations

### Defined keyframes

```css
/* USP strip marquee */
@keyframes tabblie-usp-scroll {
  0%   { transform: translateX(0); }
  100% { transform: translateX(-25%); }
}
/* 40s desktop, 22s mobile, pause on hover */

/* How-it-works connector line */
@keyframes hiw-line {
  from { transform: scaleX(0); }
  to   { transform: scaleX(1); }
}

/* How-it-works step badges (bouncy entrance) */
@keyframes hiw-badge {
  from { opacity: 0; transform: scale(0.5); }
  to   { opacity: 1; transform: scale(1); }
}
/* 0.45s cubic-bezier(0.34, 1.56, 0.64, 1), staggered */

/* How-it-works step descriptions */
@keyframes hiw-content {
  from { opacity: 0; transform: translateY(10px); }
  to   { opacity: 1; transform: translateY(0); }
}
```

### JS animations
- **Number counters** (stats, education): 1800ms duration, easeOutCubic, triggered via IntersectionObserver (threshold 0.3)
- **Scroll reveal**: `snippets/tabblie-scroll-reveal.liquid` handles generic fade-ins

### Hover micro-interactions
- Button lift: `transform: translateY(-1px)`
- Icon scale on hover: `transform: scale(1.15)`
- Newsletter button: `transform: scale(1.03)`
- CTA arrow slide: `translateX(3px)`

### Transition defaults
```css
--duration-short: 100ms;
--duration-default: 350ms;
--duration-long: 500ms;
```

---

## 9. Decorative Leaves (desktop only)

Shared SVG path, used as ambient background flourishes. Hidden on mobile via `@media (max-width: 749px) { display: none }`.

```xml
<path d="M50 5 C 25 5, 10 30, 10 55 C 10 75, 25 90, 50 95 C 50 70, 35 50, 20 40 C 40 45, 55 60, 50 95 C 75 90, 90 75, 90 55 C 90 30, 75 5, 50 5 Z"/>
```

| Section | Leaf 1 | Leaf 2 | Leaf 3 |
|---|---|---|---|
| testimonials | Yellow `#F5C842` @ 0.18, −40°, top-left | Teal `#5BB8A0` @ 0.15, 150°, bottom-right | — |
| guarantee | Teal `#5BB8A0` @ 0.12, −30°, top-left | — | — |
| ingredients | Teal @ 0.15, −25°, TL | Orange `#E8622A` @ 0.10, 140°, BR | Yellow @ 0.08, 35°, center |
| founder | Orange @ 0.10, 160°, top-right | Teal @ 0.15, −30°, bottom-left | — |
| comparison | Teal @ 0.12, 140°, top-right | Orange @ 0.08, −40°, bottom-left | — |

---

## 10. Maintenance Checklist

When modifying the theme, update this file whenever you:
- Add or remove a section file under `sections/tabblie-*.liquid`
- Change a brand color or introduce a new accent
- Add a new icon, animation, or decorative element
- Retire an old pattern (e.g. the circular logo background)

The goal: this document should stay readable as a single page and always match what is live.

## 9. Generated Imagery Style (AI images/videos — approved 2026-07-24)

Tabblie imagery is **funky, colorful and product-forward — never quiet beige "aesthetic
silence" skincare styling.**

**The formula** (validated on the PDP ingredient cards):
- Solid vivid background in a brand/product identity color (teal `#5BB8A0`, pink, yellow
  `#F5C842`, blue `#E1ECFA`-deepened) — one color per image, rotate across a set
- The product in frame where possible: the white strip (flat, dotted middle perforation) or
  the cardboard package
- Dynamic pop-art energy: objects mid-air, bursts/splashes frozen in motion, punchy
  directional light, crisp graphic shadows
- Green is allowed when the story is literally "plantaardig" (aloe/eucalyptus as playful
  props on brand teal) — but never dark-green eco-cliché or preachy
- Prompt template + live examples: `HIGGSFIELD_VIDEOS/generated/ingredient-images/prompts.md`
- Personas, product references and video recipes: `HIGGSFIELD_VIDEOS/README.md`

On-page treatment (see `sections/tabblie-ingredients.liquid`): cards in product pastel
colors (`#E2F2ED` / `#FCE8E8` / `#FDF5DD`), staggered fade-up reveal on scroll, hover =
lift + slight rotate + image zoom (bouncy `cubic-bezier(0.34, 1.56, 0.64, 1)`).

## 10. Hand-Drawn Product Illustrations (brand element — added 2026-07-24)

Each package carries a **monochrome hand-drawn doodle illustration** under the Tabblie script
wordmark, in the product's print color. These drawings ARE the brand and should return across
the site (section decorations, dividers, empty states, category headers) — prefer them over
generic decorative shapes.

| Product | Illustration | Print color on pouch |
|---|---|---|
| Wasstrips | clothesline with hanging garments (shirts, pants, socks on a sagging line) | dark red on light blue |
| Vaatwasstrips | stacked bowls/plates with a sponge and a sparkle | dark green on pink |
| Toiletstrips | (see dieline) | per identity color |

**Style traits:** playful slightly-wobbly line art with filled silhouettes, single color,
naive/hand-sketched feel — never precise geometric icons, never multi-color for these.
**Vector source:** the print dielines in `HIGGSFIELD_VIDEOS/product-reference/products/*/`
(`*-dieline.pdf`) contain the original artwork — extract vectors from there for site use
rather than redrawing.
**In AI generations:** describe as "hand-drawn [clothesline/stacked-dishes] illustration in
[dark red/dark green]" so the packaging renders faithfully.

## 11. Sticker Cards (approved card style — 2026-07-26)

The house style for stat/feature cards ("Wat traditionele merken niet vertellen" is the
reference implementation, `sections/tabblie-education.liquid`):

```css
border: solid #1F1209;                /* dark ink outline */
border-width: 2px 3.5px 3.5px 2px;    /* pen-pressure: heavier toward one corner */
/* alternate per card: even cards flip to 3.5px 2px 2px 3.5px */
border-radius: 18px;
background: #FDF6EE;                  /* or product pastel */
box-shadow: 5px 5px 0 rgba(232, 98, 42, 0.9);   /* SOLID offset shadow, accent color */
/* hover: card moves toward the light, shadow grows */
transform: translate(-2px, -4px);
box-shadow: 8px 9px 0 rgba(232, 98, 42, 0.9);
transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
```

Rules:
- Clean uniform geometry — NO wobbly radii or card tilts (tried 2026-07-26, rejected)
- The "drawn" feel comes from **varied border weight** (pen pressure), alternating the
  heavy corner per card — never from distorted shapes
- **Use the ink outline sparingly — in the details** (updated 2026-07-26): badges, icon
  chips and circles (e.g. the "30 dagen proef wassen" badge, the stat-card icon chips, the "Een twee drie" stepper nodes:
  `border: 2px solid #1F1209; box-shadow: 2px 3px 0 rgba(31,18,9,0.25)`). Full-card
  outlines only where the section carries it (e.g. the ingredient cards, the "Wat klanten
  zeggen" review carousel — `tabblie-testimonials.liquid`, 2026-09-02) — not on every grid
- Solid (non-blurred) offset shadow in an accent color — orange by default, **green
  (`rgba(56,161,105,0.9)`) when the card is the positive/Tabblie card**
- Icon chips inside cards: 36px circle, brand gradient `linear-gradient(135deg, #E8622A,
  #F5934A)` (green variant `#38A169 → #5BC98B`), white icon, soft glow, pops/rotates on hover
- Always the house bouncy easing `cubic-bezier(0.34, 1.56, 0.64, 1)`
- Pairs with the gradient-splash style (§4/newsletter) and the hand-drawn illustrations (§10)


## 12. Homepage Design Language 2026-07 ("Tierelier look" — approved 2026-07-26)

### HARD RULES — apply on EVERY page (not just the homepage)
These are founder-confirmed brand law (2026-07-26). Any page or new section that
violates them is off-brand and must be fixed:

1. **Text is very dark green `#182D20` — NEVER black** (`#000000`/`#1F1209` are retired).
   Softer copy uses rgba(24, 45, 32, x). Headings: `#182D20` or design green `#26523F`.
2. **Buttons are solid orange `#E8622A` with BOLD white text (weight 700–800)** —
   product cards, view-all, CTAs, sticky bars. White stays white on hover.
   No outline, ghost, grey, or thin-text buttons for primary actions.
3. **Bold is the default voice**: headings 700–800, button/label text 700–800,
   utility strips (announcement bar, marquees) white 800 with fat icons
   (16–18px, stroke ≥2.6). Thin/light text on colored strips is off-brand.
4. **Small orange eyebrows get pink dashes** (global custom.css rule); big headers don't.
5. Follow the recurring elements below for decoration (pills + hearts, stripe
   accents, plants on light bottom corners only, check chips).

Reference: `HIGGSFIELD_VIDEOS/product-reference/homepage-design-2026-07.jpeg` (founder design).
Live implementations: `tabblie-tierelier.liquid`, `tabblie-education.liquid`,
`tabblie-product-feature.liquid`.

### Color updates
| Token | Hex | Use |
|---|---|---|
| **Text (NEW)** | `#182D20` | ALL body/heading dark text — replaces dark earth `#1F1209` everywhere (2026-07-26) |
| **Design green** | `#26523F` | big headings, pills, check chips, ink details |
| **Plant green** | `#2C6B4E` | Matisse plant cutouts (slightly brighter so it reads green) |
| **Hero pink (deep)** | `#F08CAE` | tierelier strip background (punchier than section pink #F8BFD6) |

> The old rule "never use dark green" is RETIRED per the founder's 2026-07 design — dark
> green is now a core brand color for headings/pills/accents. Avoid only the clichéd
> "eco leaf + dark green everywhere" look; green is used graphic and playful, not preachy.

### Recurring elements
- **Two-tone chunky headings**: line 1 in design green, line 2 HUGE in white (weight 800,
  line-height ~0.95) — e.g. "Werkt als een / tierelier."
- **Pill sub-lines**: dark-green pill, white bold text + white heart (SVG heart, never emoji) —
  also used as the hero badge ("Sluit je aan bij 1.000+ huishoudens...")
- **PDP buy box (redesign 2026-07-26)**: flat green stars (#26523F) + "4,8/5 • 1.000+
  tevreden klanten", green 800 title, italic subline, 4 compact trust pills incl.
  delivery, full-width orange ATC with cart icon, green guarantee strip (#E2F2ED)
  directly under it, 76px reviewer avatar with big green stars. "Geliefd door 1.000+
  klanten" header art (heading + sparkle + colored clothesline snippet
  `tabblie-clothesline-color` + plant) sits LEFT under the social-proof card;
  UGC videos with white name/star pills stay in the right column. Package bundles
  come from the Kaching Bundles app — never build a custom package selector.
- **Orange utility strips** (announcement bar + hero marquee): white text weight 800
  (announcement 13px, marquee uppercase ~14.5px), fat white icons (16-18px, SVG
  stroke-width 2.6-2.8) — thin/light text on orange strips is off-brand
- **Brush-paint icons**: hand-painted white PNGs on colored backgrounds (flower, check, X,
  smiley — uploaded as shop images 1..4). Still used in the footer icon strip only — the
  stat-card check/X chips (EVEN EERLIJK, education) switched to the shared SVG mark
  `{% render 'tabblie-mark', kind: 'check'|'cross' %}` in an ink-outlined circle (2026-09-02)
- **White hairline dividers** between icon items (rgba(255,255,255,0.55), 1px)
- **Eyebrow dashes**: short pink strokes (#F08CAE, 22×3px, ±8° rotated) flanking uppercase
  orange eyebrows. **This is now GLOBAL**: `assets/custom.css` applies the dashes to every
  `*__eyebrow` class site-wide (2026-07-26) — new sections get it for free by naming their
  eyebrow class `tabblie-xxx__eyebrow` and adding it to the custom.css selector list
- **Sparkle strokes**: 2-3 short dark strokes (`#182D20`, 2.5px, rotated) as "ping" accents
  near icons/cards or flanking big two-tone headings (~92px on the Tierelier strip);
  NOT next to buttons (founder removed them at "Bekijk alle producten")
- **Matisse plant cutouts**: `{% render 'tabblie-plant' %}` — flat organic finger-lobes,
  cropped into section corners. Use sparingly: BOTTOM corners on light sections only
  (founder removed them from the hero top and the pink Tierelier strip, 2026-07-26)
- **Check chips**: solid dark-green circles with white checks (lists + positive stat cards);
  X chips solid orange with white X
- **CTA pills**: orange, white bold text + white heart, e.g. "Kies voor Tabblie ♥" —
  primary CTAs are BIG and bold: 18px / weight 800 / padding 17px 36px
- **Solid orange buttons everywhere**: product-card buttons (`.button-ATC`) and the
  "Bekijk alle producten" view-all link are solid `#E8622A` pills with bold white text
  (never outline/ghost); text stays WHITE on hover (theme a:hover otherwise turns it
  orange-on-orange — guarded in custom.css)
- **Plant snippet shape (2026-07-26)**: `snippets/tabblie-plant.liquid` redrawn to the
  founder-approved reference — 4 fat rounded finger-lobes (ellipses, rx 15-28) fanning out
  of a low wide mound, deep green `#26523F`, transparent background, always via inline
  `style="fill:..."` (theme CSS overrides the fill attribute)
