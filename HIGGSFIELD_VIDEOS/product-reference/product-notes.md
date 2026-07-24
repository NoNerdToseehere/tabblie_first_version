# Product & packaging facts — read before writing any Higgsfield prompt

Source: real packaging photos from the founder (2026-07-24) + PDP renders.

## Packaging (same construction for all 3 products)

- **Material: matte CARDBOARD / thick paper envelope-style pouch.** NOT plastic, no gloss,
  no crinkle. Flat, stiff, slight paper texture, soft creases possible at the edges.
  **Best one-line analogy for prompts: "like a rip-open cardboard mailing envelope
  (tear-strip style, like online-shop shipping envelopes)".**
  Founder's real-world example: corrugated cardboard shipping envelope ~235×340mm
  (https://www.amazon.nl/-/en/CP010-04-corrugated-cardboard-self-adhesive-235x340x35mm/dp/B00TX56J1C)
  — same size class and same rip-strip + fold-flap construction, just printed light blue.
- **Opening (corrected 2026-07-24): fold-over flap onto the BACK, sealed along a perforation
  on the back panel.** First use tears that perforation once; after that the flap simply lifts
  and there is a wide curved scooped mouth in the back panel — you reach in and slide a sheet
  out. **Never show the package being ripped/torn in videos** — it is already open; lift flap,
  grab sheet. The flap carries a cheeky slogan printed upside down (laundry: "Smells like
  you've got your life together"; dishwasher: "Dinner is done, so are you!"). Dielines for all
  3 products are in each product folder (`*-dieline.pdf`).
- Front layout (all products): Tabblie script wordmark → small line illustration →
  product name + count → dark rounded pills: "Plastic-free packaging", "100% biodegradable",
  "Easy to use" (laundry adds "PVA FREE" pill).
- **Per-product styling** (color changes, construction identical):
  - Wasstrips / Laundry Sheets: light-blue pouch, dark-red print, "32 strips & 64 washes"
  - Vaatwasstrips / Dishwasher sheets: pink pouch, dark-green print, "32 strips"
  - Toiletstrips: teal styling (see brand identity colors)

## The sheets/strips

- White, thin, paper-like sheets with a **dotted perforation line down the middle**.
- **One full sheet = 2 strips.** Laundry: 32 strips & 64 washes — a full sheet is a
  double dose; tear along the perforation for one wash each.
- Torn strips have one slightly serrated edge (where they separated).
- In videos: either use one full sheet (heavy load) or tear along the perforation and
  use half. Show the tear — it is a signature product moment.

## Back-flap slogans (printed upside down on the tear-off top, per product)

- Wasstrips / Laundry Sheets: "Smells like you've got your life together"
- Vaatwasstrips / Dishwasher sheets: "Dinner is done, so are you!"

## Other reference files

- `../source-videos/fullvideo.mp4` — real footage: shows package + tearing a full
  sheet into 2 strips (selfie-mirrored: label reads backwards; `-unmirrored` variant fixed)
- `../source-videos/secondvideo.mp4` — real footage: package + loading the washing
  machine (selfie-mirrored; `-unmirrored` variant fixed)

## VALIDATED RECIPE (2026-07-24) — how to get the product right in video

Test job `b93e129d-629d-4dac-8436-14c1bf8f2d61` (seedance_2_0) proved this combination renders
the cardboard package + strip-out-of-package interaction correctly:

1. References: real torn-open package photo (`407ff9e9-5782-4bac-80d5-29034a3b40a0`) +
   real strips photo (`a3c8c90d-31cf-4109-9c16-2eb605fff181`) as `image_references`.
2. Prompt must say: "MATTE CARDBOARD flat envelope-style pouch, paper texture, top edge
   torn open along the perforation leaving a slightly jagged serrated edge", "reaches into
   the torn top opening and slides out ONE thin white detergent sheet", "flat white paper-like
   sheet with a subtle dotted perforation line down the middle", and end with
   "The package stays clearly cardboard — no gloss, no plastic, no crinkle."
3. The failed v1 clips used only the flat PDP render → model invented glossy plastic. Never
   rely on the render alone; always include the real photos.
4. **Package size (founder feedback 2026-07-24): the package must read ~1.5× bigger than the
   v3 test showed.** It is a LARGE envelope — roughly A4/magazine size. Prompt language:
   "a large flat envelope about the size of a magazine, spanning from her fingertips to
   past her wrist, roughly two-thirds the width of her torso when held at chest height".

## Product personas (per-product folders — START HERE for any generation)

Each product has its own folder under `products/` with reference images, canonical generated
shots, upload IDs and a **locked product prompt block** to paste into prompts:

- `products/wasstrips/prompt.md` — blue laundry package (complete, validated)
- `products/vaatwasstrips/prompt.md` — pink dishwasher package (photos saved, not yet uploaded)
- `products/toiletstrips/prompt.md` — placeholder, no photos yet
- `products/strips-separated-and-full-sheet.jpeg` — shared strips reference (all products)

## Prompt language that helps

"matte cardboard envelope-style pouch, paper texture, perforated tear-off top edge",
"thin white detergent sheet with a dotted perforation line down the middle",
"tears the sheet in half along the perforation". Avoid: "plastic", "foil", "glossy",
"resealable", "zip".
