# Tabblie — Product Requirements Document (PRD)
*Shopify Website | Version 1.1 | April 2026*

---

## 1. Project Overview

**Project:** Tabblie Shopify Webstore
**Base Theme:** Impact (Shopify theme — exported from usetabbly.com)
**Tagline:** "Clean our world."
**Goal:** Build a brand-first DTC e-commerce website that makes Tabblie the most recognisable, loveable eco-friendly household brand — for everyone.
**Languages:** English (default) + Dutch (NL)
**Platforms:** Desktop + Mobile (mobile-first approach)

---

## 2. Business Goals

| Priority | Goal |
|---|---|
| 1 | Build a strong, recognisable brand identity online |
| 2 | Convert visitors into customers (one-time + subscription) |
| 3 | Build an email/community list for retention |
| 4 | Communicate the Tabblie Environmental Initiative clearly |
| 5 | Enable worldwide DTC sales |

**Success Metrics:**
- Conversion rate (target: >3% after first 3 months)
- Subscription uptake (target: >30% of orders on subscription)
- Avg. session duration (brand engagement indicator)
- Email list growth

---

## 3. Site Structure / Pages

### 3.1 Core Pages

| Page | Priority | Description |
|---|---|---|
| Homepage | P0 | Brand hero, product showcase, mission intro, social proof |
| Product Page (PDP) | P0 | Per-product detail with one-time + subscription toggle |
| Collection / Shop | P0 | All products — strips + tablets, filterable by category |
| Cart | P0 | Drawer cart with subscription upsell nudge |
| About Tabblie | P1 | Brand story, mission, team/founders |
| The Tabblie Initiative | P1 | Environmental initiative page — where 10% goes |
| How It Works | P1 | Explainer for strips + tablets format (what they are, how to use) |
| Starter Kit page | P1 | Bundle page: glass bottle + tablet refills — pitched as "the switch" |
| FAQ | P2 | Common questions about product, delivery, subscriptions |
| Blog | P2 | Educational/brand content (eco tips, behind the scenes) |
| Contact | P2 | Contact form |
| Account | P2 | Customer login, order history, subscription management |

### 3.2 Standard Shopify Pages (required)
- 404 Not Found
- Password (pre-launch)
- Search results
- Cart
- Login / Register / Account

---

## 4. Homepage Requirements

### Hero Section
- Full-width hero with bold headline (proposed: *"Strip the plastic."*)
- Subheadline: short brand proposition (1–2 lines)
- Primary CTA: *"Shop now"* → links to collection
- Secondary CTA: *"How it works"* → links to How It Works page
- Background: warm cream `#FDF6EE` or full-bleed lifestyle image
- Mobile: stacked layout, CTA buttons full-width

### Product Highlight Section
- Show all launch products in a grid/row — strips first, then tablets when available
- Each card: product image (with product identity color as card background accent), name, price, "Add to cart" or "Shop" button
- Subscription badge visible (e.g. "Subscribe & save X%")
- For tablet products: show the color-coded product range as a visual system

### Brand Mission Strip
- Short bold statement about the brand mission
- Eye-catching background (Tabblie Orange `#E8622A`)
- White text
- Optional: animated scrolling text banner (like Fussy/Lekker use)

### How It Works Section
- 3-step visual explainer (illustrated icons, like on packaging)
  1. Tear a strip
  2. Add to machine/toilet
  3. Done — zero plastic waste
- Clean layout, orange accent numbers or icons

### Environmental Initiative Teaser
- Short section: *"10% of every purchase goes to real environmental action"*
- Link to the full Initiative page
- Visual: something that communicates earth/ocean/plastic reduction — not clichéd

### Social Proof / Reviews
- Product star ratings
- 2–3 featured customer quotes
- Optional: UGC photo grid (Instagram-style)

### Newsletter Signup
- Incentive-led (e.g. "Get 10% off your first order")
- Email field + CTA
- Privacy note (GDPR compliant — NL market)

### Footer
- Logo + tagline
- Navigation links (Shop, About, Initiative, FAQ, Blog, Contact)
- Social media icons
- Language switcher (EN / NL)
- Payment icons
- Legal (Privacy Policy, Terms, Cookie Policy)
- GDPR cookie notice

---

## 5. Product Page Requirements

### Product Information
- Product name + short description (punchy, on-brand tone)
- Price display: one-time price + subscription price side by side
- Subscription toggle:
  - One-time purchase
  - Subscribe & save (show % discount, selectable frequency: monthly / every 2 months)
- Quantity selector
- Add to Cart button (primary, Tabblie Orange)
- Product images: packshot + lifestyle
- Key benefits: 3–4 icons with short labels (e.g. "Zero plastic", "32 loads", "Biodegradable")
- **For tablet products:** page background/hero uses the product's identity color (e.g. yellow for Kitchen Cleaner) — orange logo and branding always visible on top

### Below the Fold
- How to use (step-by-step, illustrated)
- Ingredients / What's in it (transparency)
- Environmental impact callout (e.g. "X plastic bottles saved per pack")
- Customer reviews (with star ratings)
- Related products / "Complete the bundle" upsell

### Starter Kit Page (Tablets — Phase 2)
- Dedicated bundle page: reusable glass bottle + choice of tablet refill
- Pitched as "Make the switch" — one purchase, no more plastic bottles ever
- Subscription option: tablet refills auto-ship on schedule
- Visual: show the 4 colored products side by side on glass bottles

---

## 6. Subscription Model Requirements

**App recommendation:** Shopify's native subscriptions or Recharge / Bold Subscriptions

### Subscription Features Required
- Toggle on product page: one-time vs subscribe
- Frequency options: monthly, every 2 months (configurable)
- Discount clearly shown (e.g. "Save 15% with subscription")
- Customer portal: manage, pause, cancel, swap products
- Subscription reminder emails
- Cancellation flow with save offer (e.g. "Skip a month instead?")

### Cart Behaviour
- If customer adds a one-time product, show soft nudge: *"Switch to subscription and save 15%"*
- Subscription orders should be clearly differentiated in cart/checkout

---

## 7. The Tabblie Environmental Initiative Page

### Content Requirements
- Hero: bold mission statement
- What the initiative is (Tabblie funds environmental projects — 10% of profits)
- Which types of projects are funded (anti-plastic soup, ocean clean-up, etc.)
- Impact counter (if available): e.g. "€X donated so far", "X kg plastic prevented"
- Partner organisations / funded initiatives (with logos/links)
- How it's calculated (transparent: 10% of net profits, updated quarterly)
- CTA: *"Every purchase helps — shop now"*

---

## 8. Localisation Requirements

### Languages
- **English** — default, global
- **Dutch (NL)** — full translation of all pages, product descriptions, UI

### Implementation
- Use Shopify Markets or Shopify Translate & Adapt app
- URL structure: `/en/` and `/nl/` or subdomain approach
- Language switcher visible in header and footer
- Currency: EUR primary (with auto-detection for other markets)
- GDPR compliance required for EU/NL market

### Translation Scope
- All theme UI strings (buttons, labels, headings)
- Product titles and descriptions
- Page content (About, Initiative, How It Works, FAQ)
- Email notifications
- Meta titles + descriptions for SEO

---

## 9. Navigation & Header

### Desktop Header
- Logo (left-aligned)
- Navigation: Shop | How It Works | Our Initiative | About | Blog
- Right side: Language switcher (EN/NL) | Search | Account | Cart (with item count)
- Announcement bar above header: e.g. promo message or free shipping threshold

### Mobile Header
- Logo (centred)
- Hamburger menu (left) + Cart icon (right)
- Sticky header on scroll

---

## 10. Cart & Checkout

### Cart Drawer (slide-in)
- Product image, name, quantity, price
- Subscription badge if applicable
- Subscription upsell nudge (if not subscribed)
- Subtotal + shipping info
- "Checkout" CTA (orange)
- Free shipping progress bar (e.g. "Add €X more for free shipping")

### Checkout
- Shopify native checkout
- Express checkout options (Shop Pay, Apple Pay, Google Pay)
- Trust badges near CTA (secure, eco-certified, etc.)

---

## 11. Technical Requirements

| Requirement | Detail |
|---|---|
| Base theme | Impact (Shopify) |
| Shopify version | Online Store 2.0 |
| Subscriptions | Shopify native or Recharge |
| Translation | Shopify Translate & Adapt |
| Reviews | Judge.me or Shopify native reviews |
| Email capture | Klaviyo (recommended) or Shopify Email |
| Analytics | Google Analytics 4 + Meta Pixel |
| Cookie consent | GDPR-compliant banner (NL/EU) |
| Performance | Core Web Vitals green on mobile |
| Accessibility | WCAG 2.1 AA minimum |

---

## 12. Design Requirements (Theme Customisation)

### Colors (to be applied in theme settings)
- Primary / Brand: `#E8622A` (Tabblie Orange) — always used for logo, CTAs, brand elements
- Background: `#FDF6EE` (Warm Cream)
- Text: `#1F1209` (Deep Earth)
- Product: All-Purpose — `#E8622A` (Orange)
- Product: Kitchen Cleaner — `#F5C842` (Sunny Yellow)
- Product: Bathroom Cleaner — `#5BB8A0` (Soft Teal)
- Product: Hand Soap — `#F2A0A0` (Blush Pink)

### Fonts (to be loaded via theme)
- Display / Headings: Fraunces (Google Fonts)
- Body: DM Sans (Google Fonts)

### UI Style
- Rounded corners on buttons (8–12px radius)
- Soft, warm box shadows (not harsh black shadows)
- Generous padding/white space
- Orange CTAs always — no grey or muted primary buttons
- Playful illustrated elements where possible (section dividers, icons)

---

## 13. Out of Scope (Phase 1)

- Custom loyalty/rewards program
- Wholesale / B2B portal
- Mobile app
- Live chat (can be added later)
- AR/3D product viewer

---

## 14. Launch Checklist

- [ ] All 3 products live with descriptions, images, pricing
- [ ] Subscription model configured and tested
- [ ] EN + NL translations complete
- [ ] Initiative page live with content
- [ ] GDPR cookie banner active
- [ ] Google Analytics 4 + Meta Pixel firing
- [ ] Email capture flow connected to Klaviyo
- [ ] Mobile tested on iOS Safari + Android Chrome
- [ ] Core Web Vitals passing
- [ ] All legal pages live (Privacy, Terms, Cookie Policy)
- [ ] Domain connected and SSL active
