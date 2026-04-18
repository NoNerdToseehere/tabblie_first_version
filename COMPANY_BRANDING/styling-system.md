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

## 2. Typography

### Single typeface
**Plus Jakarta Sans** — Google Fonts, weights 400/500/600/700 with italic 400/600. Loaded once and used for both `--heading-font-family` and `--text-font-family`. Do not introduce a second face.

### CSS variables
```css
--heading-font-weight: 600;
--text-font-weight: 400;
--heading-letter-spacing: -0.02em;
--text-letter-spacing: 0em;
```

### Type scale (live `clamp()` values)

| Element | CSS |
|---|---|
| Page hero H1 | `clamp(2.8rem, 6vw, 5.2rem)` |
| Section H2 | `clamp(2.2rem, 4vw, 3.4rem)` |
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
- Eyebrows always orange `#E8622A`, weight 600–700, letter-spacing `0.1em`, uppercase
- Never drop below 400 weight (accessibility)
- Body text minimum 16px on mobile to avoid iOS zoom on inputs

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
| Star (unicode ★) | Review rating | `#E8622A` | testimonials |
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
| `tabblie-favicon.png` | 256×256 orange "T" square, browser tab |
| `tabblie-favicon.svg` | Vector favicon alternative |

**Never:**
- Use emojis anywhere on the site
- Recolor icons outside the palette above
- Wrap the wordmark in a circle, pill, or badge

---

## 4. Buttons & CTAs

### Primary CTA (solid orange pill)
```css
background: #E8622A;
color: #FFFFFF;
padding: 12px 32px;
border-radius: 100px;
font-size: 14–15px;
font-weight: 600–700;
border: none;
transition: background 0.2s ease;

/* hover */
background: #D4531D;
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
| `20px` | Large image containers (founder portrait, guarantee visual) |
| `16px` | Cards, ingredient tiles, testimonial cards, comparison table |
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
| 720  | Impact, testimonials inner |
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
