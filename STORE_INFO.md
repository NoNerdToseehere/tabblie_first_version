# STORE_INFO.md — Tabblie Store & Workflow Facts

Single source of truth for store identifiers, git setup, and Shopify workflow details.
Update this file whenever any of these facts change.

---

## Store

| Fact | Value |
|---|---|
| Store name | Tabblie |
| Vanity domain (live site) | https://tabblie.com |
| **Permanent domain (use for CLI!)** | `7b9f5e-cc.myshopify.com` |
| Shopify store ID | `88961286493` |
| Currency | EUR |
| Location | Utrecht, NL |
| Admin URL | https://admin.shopify.com/store/7b9f5e-cc |

> ⚠️ **Shopify CLI always needs the permanent domain**, never the vanity domain:
> `shopify theme list --store 7b9f5e-cc.myshopify.com`
> Using `--store tabblie.com` fails with "not authorized … tabblie.com.myshopify.com".

## Git / GitHub

| Fact | Value |
|---|---|
| Repo | https://github.com/NoNerdToseehere/tabblie_first_version |
| Remote | `origin` (fetch + push) |
| Branch | `main` (only branch) |
| Git user | NoNerdToseehere |
| Local path | `/Users/projects/Desktop/shopify_build_ai/shopifytheme2` |

## Shopify ↔ GitHub Integration

- The theme named **`tabblie_first_version/main`** in the Shopify admin is connected to this repo via Shopify's GitHub integration — pushes to `main` auto-deploy to that theme, and edits made in the Shopify theme editor on that theme are auto-committed back to `main` (commits titled "Update from Shopify for theme tabblie_first_version/main").
- **Duplicating a theme in the Shopify admin breaks this link** — the copy is a plain theme with no GitHub connection. Changes made on a copy exist only in Shopify. If it happens again: `shopify theme pull` from the copy, commit, push, wait for the integration to deploy, then `shopify theme publish` the connected theme.
- ✅ **Resolved 2026-07-24:** editor edits made on a disconnected copy were pulled into git (commit `c75c3c9`) and the connected theme was republished. Live theme = `tabblie_first_version/main` (#201232744797) again.
- The old copy "Copy of tabblie_first_version/main" (#206425522525) still exists unpublished as a backup — safe to delete once the live site is confirmed OK. **Make all future edits on the connected theme, not on copies.**
- **Storefront is password-protected** (pre-launch) — you can't verify content via curl/public URL; use the admin preview or theme editor links.

## Theme

- Base theme: Halo (Online Store 2.0), files at repo root so the GitHub integration detects them.
- **Preview-before-push workflow:** edit locally → `shopify theme dev --store 7b9f5e-cc.myshopify.com` → review at http://127.0.0.1:9292 (hot-reloads on save; also prints a shareable `?preview_theme_id=` link for phone testing) → only commit & push once approved. Pushing = deploying to the live theme, so never push unreviewed visual work.
- Pull a specific theme: `shopify theme list --store 7b9f5e-cc.myshopify.com` to get IDs, then `shopify theme pull --store 7b9f5e-cc.myshopify.com --theme <ID>`
- CLI auth: device-code login expires in minutes — run `shopify auth login` in a terminal you're watching.

## Optimization Mandate — applies to EVERY change

We optimize everything, always — no exceptions:

1. **SEO** — correct heading hierarchy (one `h1` per page), meta titles/descriptions, descriptive alt text, structured data (JSON-LD), descriptive anchor text. Full rules → `CLAUDE.md` § SEO.
2. **Speed** — Core Web Vitals green on mobile: no render-blocking resources, lazy-load below-the-fold images, Shopify image CDN with `image_url`, explicit dimensions against layout shift. Full rules → `CLAUDE.md` § Performance.
3. **Conversion** — CTA above the fold, trust signals near buy decisions, low friction to checkout, product always visible. Full rules → `CLAUDE.md` § Conversion.

Every new section, page, or copy change gets checked against all three before it ships.

**ALWAYS fully responsive — no exceptions.** Everything must look and work perfectly on every device and screen size: phones (375px/390px), tablets/iPad (768px/1024px), laptops (1280px) and wide desktops (1440px+). Mobile-first CSS, no horizontal scroll anywhere, touch targets ≥ 44px. A change that only works on desktop is a bug, not a finished task — verify at least 390px + desktop (Playwright screenshots against `shopify theme dev`) before committing.

**URL paths / handles:** all paths must be SEO-optimized, Dutch, and descriptive — `/pages/duurzaamheid`, `/pages/veelgestelde-vragen`, `/pages/alle-producten`, `/products/tabblie-wasstrips` — never English or generic handles (`foundation`, `faqs`, `shop`, `tabblie-laundry`). When renaming a handle: update every internal link in the theme AND create a URL redirect (admin → urlRedirectCreate) from the old path.

**File naming:** always use SEO-friendly, descriptive, structured file names — lowercase kebab-case that says what the file is (`tabblie-wasstrips-doosje-hero.jpg`, not `IMG_4521.jpg` or `Screenshot 2026-...png`). Applies to images, assets, snippets, and section files alike.

**Cleanup — delete, don't leave lying around:** never keep files, assets, code or settings that nothing uses. This covers temporary artifacts (screenshots, test scripts, scratch exports, one-off conversions) *and* anything that has stopped being used: superseded images, dead CSS, unreferenced snippets, placeholder assets that were never adopted. Delete it in the same session you notice it, in the repo *and* in temp locations, and remove any doc rows describing it so the docs don't advertise something that no longer exists.

Why it matters: every unused asset is still uploaded to the theme and served from the CDN, so it costs load time; and a stale file is a trap — someone (or some future session) wires it up believing it's current. A placeholder favicon that wasn't the real brand mark sat in `assets/` for months for exactly this reason.

Before deleting, grep the whole repo for the filename to confirm nothing references it — including the MD docs.

**Keep the MD files up to date:** whenever a change alters something these docs describe (fonts, colors, claim language, URLs, store facts, workflow rules), update the relevant MD file(s) in the same session — `STORE_INFO.md`, `CLAUDE.md`, `COMPANY_BRANDING/CLAUDE.md` and `COMPANY_BRANDING/styling-system.md` must never contradict the live site. If it's unclear whether a change is a new standard or a one-off experiment, **ask before writing it into the docs**.

**Always git commit & push:** git is the deploy pipeline — the GitHub integration only puts committed, pushed work on the live theme. Never end a work session with finished changes sitting uncommitted; commit and push as soon as a change is verified. Unpushed = not live.

## Related docs

- Working instructions & brand rules → `CLAUDE.md`
- Brand document → `COMPANY_BRANDING/brand-document.md`
- PRD → `COMPANY_BRANDING/PRD.md`
- Style system → `COMPANY_BRANDING/styling-system.md`
