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
- **Duplicating a theme in the Shopify admin breaks this link** — the copy is a plain theme with no GitHub connection. Changes made on a copy exist only in Shopify.
- ⚠️ **Current situation (2026-07-24, unresolved):** the live/published theme is a *copy* made in the admin with manual edits — it is NOT GitHub-connected. Plan: `shopify theme pull` from the live copy into this repo, review + commit the diff, then republish the GitHub-connected theme to restore sync.

## Theme

- Base theme: Halo (Online Store 2.0), files at repo root so the GitHub integration detects them.
- Dev preview: `shopify theme dev --store 7b9f5e-cc.myshopify.com`
- Pull a specific theme: `shopify theme list --store 7b9f5e-cc.myshopify.com` to get IDs, then `shopify theme pull --store 7b9f5e-cc.myshopify.com --theme <ID>`
- CLI auth: device-code login expires in minutes — run `shopify auth login` in a terminal you're watching.

## Related docs

- Working instructions & brand rules → `CLAUDE.md`
- Brand document → `COMPANY_BRANDING/brand-document.md`
- PRD → `COMPANY_BRANDING/PRD.md`
- Style system → `COMPANY_BRANDING/styling-system.md`
