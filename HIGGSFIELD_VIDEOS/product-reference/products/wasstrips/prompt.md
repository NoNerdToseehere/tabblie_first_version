# Wasstrips / Laundry Sheets — product persona

## Locked product prompt block (paste into every generation)
"the light-blue 'Tabblie Laundry Sheets' package: a large MATTE CARDBOARD flat envelope about
the size of a magazine — constructed like a rip-open cardboard mailing envelope (tear-strip
style, like online-shop shipping envelopes), paper texture. FRONT: 'Tabblie' logo in dark red script, clothesline
illustration, 'Laundry Sheets — 32 strips & 64 washes', dark-red rounded pills. BACK: white
rounded info panels with dark-red text and a 'How much do you need?' dosage chart. The top
closes with a fold-over flap onto the back, printed 'Smells like you've got your life together';
the flap has already been opened along its perforation, and beneath it the back panel has a wide
curved scooped mouth opening. To take a sheet she simply lifts the flap and slides ONE thin white
paper-like detergent sheet out through the open mouth — nothing is torn on camera. Each sheet
has a subtle dotted perforation line down the middle (one full sheet = 2 strips, tear along the
perforation for half a dose). The envelope's SIDE EDGES are crisp flat glued seams, like a
cardboard shipping envelope — the sides stay rigid and flat when the package turns, never
collapsed, folded inward, or pinched. The package stays clearly cardboard — no gloss, no
plastic, no crinkle."

## Video anti-artifact rules (learned from v6 QA, 2026-07-24 — include in every video prompt)
- "The envelope always stays FLAT like a stiff cardboard mailer — it NEVER opens up like a
  box or carton; the only opening is the narrow curved mouth slot at the top of the back panel."
- "Exactly ONE single sheet comes out — never a second sheet hanging below or extra sheets."
- "The printed info panels on the back are small and printed flat on the back panel — never
  an oversized white text panel or separate text side."
- "The sheet goes directly into the washing machine drum on top of the clothes — NEVER into
  the detergent drawer."
- "No Tabblie logo or text anywhere except on the package itself (not on the washing machine)."
- "No on-screen text, captions or subtitles." (Seedance likes to burn in garbled UGC captions.)
- "The washing machine is a plain unbranded white machine."
- **Staging tip (founder, 2026-07-24): avoid the grab-out-of-package action when possible —
  it is the hardest part for the model. Prefer: package shown FRONT to camera (closed), the
  sheet already in the other hand, machine already running. Only show the grab when the scene
  truly needs it.**

## Opening mechanics (CRITICAL — founder correction 2026-07-24)
Construction is a rip-open cardboard mailing envelope (see dieline + photos). The exact
opening sequence, in the founder's words:

1. **Rip the perforated strip on the BACK** (one-time, first use only)
2. **Fold the remaining flap up toward the top** — the flap reads
   "Smells like you've got your life together"
3. **Reach inside** through the wide curved scooped mouth in the back panel and slide a sheet out

In videos of an already-opened package: NO ripping — just step 2 + 3 (flip the flap up, grab
a sheet through the mouth). Hold the package front-label to camera while doing it. Only show
step 1 if the scene is explicitly a first-time unboxing/opening.

## Size rule (founder-approved 2026-07-24)
Magazine-size. In hand: spans from fingertips to past the wrist, roughly two-thirds the width
of a torso when held at chest height.

## Reference images (Higgsfield media/job IDs)
| File | ID | Note |
|---|---|---|
| wasstrips-backside-open-mouth.jpeg | media `2810ac79-0cf9-4804-b8e9-5b6bc743fad2` | REAL photo, opened: flap lifted + wide scooped mouth — PRIMARY reference for the grab-a-sheet interaction |
| wasstrips-backside-flap-open.jpeg | (not uploaded) | REAL photo, back panel flat with flap open, info panels readable |
| wasstrips-dieline.pdf | (local only) | print dieline — exact layout of front/back/flap |
| wasstrips-real-package-open-back.jpeg | media `407ff9e9-5782-4bac-80d5-29034a3b40a0` | REAL photo, opened, back slogan — material reference |
| ../strips-separated-and-full-sheet.jpeg | media `a3c8c90d-31cf-4109-9c16-2eb605fff181` | REAL strips: 2 separated + 1 full with perforation — always pass with the package ref |
| wasstrips-package-render.jpg | media `3aeefe0e-ca7c-4df6-a4a8-1e99f23e2ff8` | PDP render, front label (label detail only — NEVER alone, causes plastic look) |
| kit-package-front.png | job `695bc0de-34c2-4a92-bbd0-8230e9392959` | canonical generated front |
| kit-package-open-strip-out.png | job `108415cc-7f1d-48b1-8a0c-ae23f2a3ed51` | canonical generated open + strip out |
| kit-strips-layout.png | job `35d3de5c-b168-4a4c-bd79-87b53f80cca0` | canonical generated strips layout |

## Identity colors
Pouch #E1ECFA-ish light blue, print dark red. Site accents: orange #E8622A / card bg #FDEEE6.

## Tearing rule (founder, 2026-07-24)
The tear is trivial and must look trivial: hold the full sheet with both hands, one half in
each hand, and tear straight down the middle perforation in ONE smooth motion — two equal
rectangular halves, clean straight serrated edge. Never crumple, twist, fold or tear diagonally.
Prompt: "she tears the sheet in one smooth motion straight along the middle perforation line,
splitting it into two equal rectangular halves".
