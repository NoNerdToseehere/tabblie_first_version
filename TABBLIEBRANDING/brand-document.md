# Tabblie — Brand Document
*Version 2.0 | April 2026*

---

## 1. Brand Overview

**Brand Name:** Tabblie (capital T, rest lowercase — always written "Tabblie", never "tabblie" or "TABBLIE")
**Category:** Eco-friendly household cleaning products
**Format:** Dissolvable strips (launch range) + cleaning tablets with reusable glass bottles (Phase 2)
**Tagline (NL, primary):** "Schoonmaken, opnieuw uitgevonden."
**Slogan (NL):** "Tabblie, kind kan de was doen."
**Markets:** Netherlands & Belgium (primary), English planned later
**Positioning:** Affordable, aesthetic, eco-friendly household products for everyone — not just the committed environmentalist.

---

## 2. Mission & Purpose

> Tabblie exists to prove that eco-friendly doesn't have to mean expensive, ugly, or inconvenient.

We make switching to sustainable household products a no-brainer — better for the planet, better for your wallet, and actually something you want to display in your home.

**The problem we solve:**
Most eco-friendly products fall into one of two traps: they look like they belong in a health food shop from 2003 (bland, brown, preachy), or they cost so much that only a niche audience can afford them. Tabblie breaks both patterns.

**What we stand for:**
- The planet deserves better — and so do you
- Sustainability should be the easy, affordable default — not a premium sacrifice
- Good design and good values are not opposites
- Everyone can make a difference, not just the hardcore eco crowd

---

## 3. Brand Positioning

| | Tabblie | Traditional Eco Brands | Regular Brands |
|---|---|---|---|
| Price | Competitive / better than non-eco | Premium | Low–mid |
| Aesthetics | Vibrant, modern, playful | Utilitarian, "natural" | Generic |
| Audience | Everyone | Niche eco-conscious | Mass market |
| Feel | Exciting | Virtuous / preachy | Functional |

**Closest competitors for reference:**
- [Fussy](https://www.getfussy.com/) — tone & energy (cheeky, bold, design-led)
- [The Lekker Company](https://thelekkercompany.com/) — warmth, natural materials, Dutch roots
- [Mother's Earth NL](https://nl.mothersearth.com/) — product category (strips), but Tabblie is more accessible & designed for everyone

---

## 4. Target Audience

**Primary:** Ages 22–42, design-conscious, urban/suburban, moderate eco-awareness. They care about the environment but won't sacrifice aesthetics or break the bank. They're not activists — they just want to make better choices without it being a whole thing.

**Secondary:** Families looking to reduce plastic waste without overhauling their entire lifestyle.

**Who we are NOT for:** The hardcore zero-waste community who already has everything figured out (though they're welcome too).

**Audience mindset:** *"I want to do better for the planet, but I'm not going to pay €25 for laundry detergent that comes in a hessian sack."*

---

## 5. Products

### Phase 1 — Strips (Launch Range)

| Product | Description | Packaging |
|---|---|---|
| Eco Friendly Laundry Strips | 32 loads per pack | Kraft paper pouch |
| Eco Friendly Dishwasher Strips | 32 loads per pack | Kraft paper pouch |
| Eco Friendly Toilet Strips | 32 loads per pack | Kraft paper pouch |

**Pricing:** ~€15–20 per pack (single), with subscription discount.
**Packaging:** Kraft paper pouches — no plastic waste, fully biodegradable.

### Phase 2 — Cleaning Tablets + Reusable Glass Bottles

Dissolvable cleaning tablets paired with a reusable glass spray bottle. Buy the bottle once, refill with tablets forever. Zero plastic. Cheaper than conventional cleaners.

| Product | Identity Color | Hex |
|---|---|---|
| All-Purpose Cleaner | Tabblie Orange | `#E8622A` |
| Kitchen Cleaner | Sunny Yellow | `#F5C842` |
| Bathroom Cleaner | Soft Teal | `#5BB8A0` |
| Hand Soap | Blush Pink | `#F2A0A0` |

**Color system logic:**
- The Tabblie logo and brand typography appear in orange on every product — always
- Each cleaning tablet product has its own identity color used on the label band and product accent — just like the kraft bags use orange on a neutral base, the glass bottles use orange branding on a colored label
- This makes the range instantly navigable on a shelf or screen while keeping the brand cohesive

**Pricing:** Tablets cheaper than conventional (non-eco) cleaning products.
**Purchase models:** One-time purchase + subscription (monthly/bi-monthly).
**Packaging:** Cardboard tablet refill pack — no plastic waste. Glass bottle sold separately as a starter kit.

---

## 6. Color Palette

### Primary Colors

| Name | Hex | Usage |
|---|---|---|
| Tabblie Orange | `#E8622A` | Primary brand color, CTAs, logo, highlights |
| Warm Cream | `#FDF6EE` | Page backgrounds, cards — echoes kraft packaging |
| Deep Earth | `#1F1209` | Primary text, dark backgrounds |

### Secondary / Accent Colors

| Name | Hex | Usage |
|---|---|---|
| Soft Teal | `#5BB8A0` | Accent, eco badges, secondary CTAs |
| Sunny Yellow | `#F5C842` | Playful highlights, tags, fun elements |
| Blush Coral | `#F28C5E` | Softer orange for hover states, gradients |
| White | `#FFFFFF` | Clean sections, product cards |

### Product Identity Colors (Phase 2 Tablets)

| Product | Color Name | Hex |
|---|---|---|
| All-Purpose Cleaner | Tabblie Orange | `#E8622A` |
| Kitchen Cleaner | Sunny Yellow | `#F5C842` |
| Bathroom Cleaner | Soft Teal | `#5BB8A0` |
| Hand Soap | Blush Pink | `#F2A0A0` |

### Color Rules
- **Orange is always the brand anchor** — logo, typography, and icons appear in orange on every product and every page, no exceptions
- Each product has its own identity color for label backgrounds and product accents — orange brand elements sit on top
- Backgrounds should be warm cream (not cold white `#FFFFFF`) for most web sections
- Never use dark green as a primary — it reads as "typical eco brand"
- Product identity colors can be used as section backgrounds on product pages
- Text on orange backgrounds: always white
- Text on cream backgrounds: Deep Earth `#1F1209`

---

## 7. Typography

### Fonts

Tabblie uses **one font across the entire site**: Plus Jakarta Sans (Google Fonts, weights 400/500/600/700 including italic 400/600). It powers both the `--heading-font-family` and `--text-font-family` CSS variables — no serif mix, no secondary display face.

| Role | Font | Weight | Letter-spacing |
|---|---|---|---|
| Brand wordmark | Custom (bold grotesk) — PNG/SVG asset, not web font | — | — |
| Display / Hero headlines | Plus Jakarta Sans | 600 | −0.02em |
| Section H2 | Plus Jakarta Sans | 600 | −0.02em |
| Body / UI text | Plus Jakarta Sans | 400 | 0em |
| Eyebrow / uppercase labels | Plus Jakarta Sans | 600–700 | 0.1em, uppercase |
| Small / caption | Plus Jakarta Sans | 400–500 | 0.03em |

### Type Scale (live values — fluid with `clamp()`)

| Element | CSS |
|---|---|
| Page hero heading | `clamp(2.8rem, 6vw, 5.2rem)` |
| Section H2 | `clamp(2.2rem, 4vw, 3.4rem)` |
| Newsletter heading | `clamp(2.6rem, 5vw, 4rem)` |
| Card H3 | `clamp(1.25rem, 2vw, 1.5rem)` |
| Body | 14–16px (16px on mobile to avoid iOS zoom) |
| Eyebrow | 13px fixed |

### Line Heights
- Headings: `1.1`–`1.15` (tight, punchy)
- Body: `1.6`–`1.7` (generous, readable)

### Typography Rules
- Brand name is always written **"Tabblie"** — capital T, rest lowercase. Never "tabblie" all-lowercase, never "TABBLIE" in caps.
- One typeface only (Plus Jakarta Sans) — do not introduce a second display face
- Body text: 16px minimum on mobile (prevents iOS zoom on input focus)
- Avoid weights below 400 — keeps accessibility strong
- Eyebrows are always uppercase with `0.1em` letter-spacing and orange fill

---

## 8. Tone of Voice

**In one sentence:** Tabblie talks like a witty, environmentally-aware friend — not a lecturer, not a corporation.

### Personality Traits
- **Cheeky** — willing to poke fun at the status quo ("Who said eco had to be boring?")
- **Direct** — says what it means, no fluff
- **Inclusive** — invites everyone in, never guilt-trips
- **Optimistic** — focuses on possibility, not doom and gloom
- **Grounded** — honest about what the product is, no greenwashing

### Tone Examples

| Context | Don't say | Do say |
|---|---|---|
| Product headline | "Sustainable dishwasher detergent for the conscious consumer" | "Your dishwasher called. It wants strips." |
| Eco message | "Every purchase reduces your carbon footprint" | "32 loads. Zero plastic. You're kind of a big deal." |
| Subscription CTA | "Subscribe to our auto-replenishment service" | "Set it, forget it, save the planet." |
| About brand | "We are committed to sustainability" | "Eco doesn't have to be a personality. It can just be Tuesday." |

### Writing Rules
- Short sentences. Real words. No jargon.
- Humor is warm and inclusive — never at the customer's expense
- Never preach, shame, or use guilt as motivation
- Eco credentials are facts, not virtue signals
- Use "you" — speak directly to the person, not at an audience

---

## 9. Tagline & Slogans

> **Tagline (primary, NL):** "Schoonmaken, opnieuw uitgevonden."
> **Slogan (NL):** "Tabblie, kind kan de was doen."

The tagline lives on the homepage hero; the slogan appears in packaging copy, the footer, and storytelling sections. Both are Dutch by default — English equivalents are only used if/when we localise.

**Supporting copy lines** (campaigns, hero sections, ads):
- *"Scheur, gooi, klaar."* (3-step mantra)
- *"Eén strip vervangt één plastic fles."*
- *"Geen plastic, geen rommel, geen excuses."*
- *"32 wasbeurten. Nul plastic."*

---

## 10. The Tabblie Environmental Initiative

**Name:** TBD (e.g. "The Strip Fund" / "Tabblie for Earth")
**Commitment:** 10% of all profits go toward funding environmental initiatives
**Focus:** Fighting plastic pollution (Plastic Soup) and broader environmental projects
**Model:** Tabblie's own initiative — funding multiple external environmental organizations, not tied to one foundation

**Key messages:**
- Every purchase directly funds real environmental action
- Transparent — customers can see where money goes
- Not a marketing gimmick — baked into the business model from day one

---

## 11. Visual Style Guidelines

### Photography & Imagery
- **Bright, airy, natural light** — no dark moody shots
- Show products in real home settings (kitchen counter, bathroom shelf, laundry room)
- **People** should look real, diverse, happy — not polished stock models
- **Lifestyle shots** should feel like a friend's Instagram, not an ad campaign
- Avoid: forest/nature clichés, green leaves as props, hands holding globes

### Illustration & Icons
- Playful line-drawn icons (as seen on packaging) — one per product
- Organic shapes, slightly imperfect lines — human, not algorithmic
- Orange on cream or white backgrounds preferred

### Layout & Design
- Clean, generous white space — let the color and product breathe
- Cards and sections with soft rounded corners
- Subtle textures allowed (e.g. paper grain on backgrounds) — nods to kraft packaging
- Avoid harsh shadows — use soft, warm shadows with slight orange tint

### Logo System

The brand mark is a **bold orange wordmark**: the word "Tabblie" (capital T, rest lowercase) rendered as a chunky, rounded grotesk in Tabblie Orange `#E8622A` on light backgrounds. It reads as confident and modern — not script, not serif, not soft.

| Asset | File | Usage |
|---|---|---|
| Full wordmark | `tabblie-logo.svg` / `tabblie-logo.png` | Site header, footer, marketing — anywhere there's room for the full name |
| Small mark (orange "T") | `tabblie-logo-small.png` | Sticky mobile navbar, compact UI, social avatars, app icons, packaging stickers |
| Favicon | `tabblie-favicon.png` (256×256, orange "T" square) | Browser tab |

**Logo rules:**
- The wordmark sits on its own — **no circle, badge, or container around it**. (Previous circular-background treatments are retired.)
- Always written "Tabblie" — capital T, rest lowercase. Never "tabblie", never "TABBLIE".
- Minimum clear space: equal to the height of the capital "T"
- On light/cream backgrounds: orange `#E8622A`
- On dark or photographic backgrounds: white
- Never stretch, rotate, recolour, or add effects (drop shadows, outlines, bevels)
- Never swap the wordmark for all-lowercase or the old lowercase serif mark

---

## 12. Brand Don'ts

- Don't render the logo inside a circle, pill, or badge — the wordmark stands alone
- Don't write the brand name as "tabblie" (all-lowercase) or "TABBLIE" (all-caps) — it's always "Tabblie"
- Don't introduce a second typeface — Plus Jakarta Sans does everything
- Don't use dark green as a primary color
- Don't use guilt or fear messaging around climate
- Don't make the product seem like a sacrifice
- Don't use overly technical eco-language without explanation
- Don't show the brand as exclusive, niche, or "for eco people"
- Don't use cold blues or grays as dominant colors
- Don't use emojis anywhere — always SVG icons (see `styling-system.md`)
- **Don't claim "plasticvrij" / "plastic-free" / "100% plastic free"** — the products are not 100% plastic-free. The correct, honest claim is **"geen plasticafval"** (NL) / **"no plastic waste"** (EN). The difference matters: we eliminate plastic *waste* (no plastic bottles, packaging, or microplastics ending up in landfill), not every plastic molecule in the formula. Greenwashing-adjacent claims damage trust.
