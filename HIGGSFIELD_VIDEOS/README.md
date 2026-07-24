# HIGGSFIELD_VIDEOS — Tabblie UGC asset library

Reusable personas, prompts, references and generated videos for Tabblie UGC content
made with the Higgsfield MCP. **Videos land here first for review — only approved clips
get copied to `/assets` and wired into the theme.**

## Folder layout

```
personas/<name>/           → portrait PNG + prompt.md (exact prompt, model, job id)
product-reference/         → package reference images + product-notes.md (MUST-READ before prompting)
source-videos/             → real UGC footage from the founder (input for person/background swaps)
generated/v1-2026-07-24/   → first generation round (currently live on the wasstrips PDP)
```

## Workflow that worked (v1, 2026-07-24)

1. **Portraits:** model `soul_2` (→ `text2image_soul_v2`), aspect 1:1, quality 2k.
   Selfie-style prompt pattern, see each `personas/<name>/prompt.md`.
2. **Videos:** model `seedance_2_0`, 9:16, 10s, 720p, audio on (~45 credits/clip).
   Pass the package photo as `image_references` AND the persona portrait (job id works
   directly as media value) so the same face appears in the video.
3. Always add `declined_preset_id` if Higgsfield suggests an off-brand preset.
4. QA: pull frames with ffmpeg, check package fidelity + persona match, then verify
   on the PDP at 390px + desktop before commit.

## Key Higgsfield IDs (reusable as `medias[].value`)

| Asset | ID | Type |
|---|---|---|
| Wasstrips package photo (PDP render, blue) | `3aeefe0e-ca7c-4df6-a4a8-1e99f23e2ff8` | media_id |
| Lisa portrait | `b1fe0fd0-f907-4dfd-b499-9a671befad44` | job_id |
| Marieke portrait | `d8ad42d6-37f2-46a6-9e29-030c40347794` | job_id |
| Sophie portrait | `10a14396-77f2-4c37-b329-0df8da100d89` | job_id |
| Sanne portrait | `5244bff4-d094-4c12-9dba-64867cbe9098` | job_id |
| Video: Lisa laundry room (v2, identity-matched) | `c6095da6-fd5b-47fb-a558-865544754a12` | job_id |
| Video: Marieke — kind doet de was | `2701b306-a18c-4927-ac74-b661fc6433ad` | job_id |
| Video: Sophie — closeup POV | `d1490ae8-a90b-4234-83a7-f58337d8b284` | job_id |

## Workflow — recast real footage (v2, 2026-07-24)

Swap the person (and optionally background) in real UGC footage while keeping the motion:

1. **Un-mirror** selfie footage first (`ffmpeg -vf hflip`) so the package label reads correctly.
2. Upload the video (`media_upload` → curl PUT → `media_confirm`).
3. Make a **character still** with `nano_banana_pro` (persona portrait job_id as `image` media,
   9:16). If the background should change too, describe the new scene in this still —
   it becomes the video background.
4. Run `motion_control` (Kling 3.0): `image_id` = still, `motion_video_id` = footage.
   `scene_control: "image"` = take background from the still; `"video"` = keep the footage's
   own background. No prompt needed. Audio from the source is NOT carried over.

| v2 asset | ID | Type |
|---|---|---|
| fullvideo un-mirrored (talk + tear demo, 19s) | `4cf22b54-a490-4a44-a0ad-3b12342675c9` | media_id |
| secondvideo un-mirrored (machine loading, 35s) | `e53093f6-7d27-4d48-86ab-3ea1391862fb` | media_id |
| Lisa standing in plant-filled laundry room (still) | `a3b5bb1b-8601-4f9f-bb61-a893bd3ca994` | job_id |
| Marieke standing (still) | `33afe359-736a-4611-85a9-6a86cf341878` | job_id |
| secondvideo trimmed to 19s (Kling motion-control limit is ~20s — 30s and 35s both FAILED) | `57a2ca38-be31-47ef-b61e-f83512a19c9b` | media_id |
| Lisa holding package in plant-filled laundry room (still) | `cbf4f9ff-c59c-4cf6-8130-d43ad95c67a0` | job_id |
| Recast: Lisa ← fullvideo v1 — FAILED LESSON: still had no package → she gestures with empty hands | `7154ef39-7c2f-46c7-b96a-f88326292e27` | job_id |
| Recast: Lisa ← fullvideo v2 (still WITH package) | `a502fe5d-10d2-4a69-9685-338980d0f154` | job_id |
| Recast: Marieke ← secondvideo 19s (background kept) | `e4fd5e15-2287-446b-874a-94b3abbcf612` | job_id |

**Lessons:** (1) `scene_control: "image"` takes props from the STILL — if the persona must
hold the product, the character still must already show them holding it. (2) Kling
motion-control caps the driving video around 20s — trim longer footage first.

## v3/v4 — validated cardboard recipe (2026-07-24)

`generated/v3-cardboard-test/` proved the recipe (see `product-reference/product-notes.md`);
`generated/v4-pdp-clips/` are the corrected PDP clips made with it — real package + strips
photos as references, cardboard/no-plastic language, Lisa identity ref in her clip:

| v4 clip | job_id |
|---|---|
| lisa-laundry-room.mp4 | `150310b8-05ea-437c-86e6-a1380f59ec76` |
| marieke-kind-doet-de-was.mp4 | `21c73adb-695e-4a93-9ec0-6ac5daec77df` |
| sophie-closeup-pov.mp4 | `ae75b73b-e655-4cf8-9d11-50e0847841b6` |
| cardboard-strip-out-test.mp4 (v3) | `b93e129d-629d-4dac-8436-14c1bf8f2d61` |

## Known issue in v1 (fix in next rounds)

The v1 videos show the package as a glossy **plastic** pouch and generic sheets.
The real product is **matte cardboard** with a perforated tear-off top, and the sheets
are full sheets with a center perforation (tear into 2 strips). Read
`product-reference/product-notes.md` before writing any new prompt.
