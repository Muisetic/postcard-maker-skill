---
name: postcard-maker
description: Create or revise print-ready travel postcards from user photos. Use for single or batch postcard generation, including photo enhancement, orientation-safe 3:2/2:3 cropping, the fixed postcard front design, coordinated visual-memory backs, and corrections to existing postcards. Preserve each source photo's original portrait/landscape orientation. Do not use for generic cards, unrelated posters, or photo-only edits that are not postcard tasks.
---

# Postcard Maker

Turn a user-provided travel photograph into a coordinated postcard front and back.

The fixed visual concept is:

> Front = polished travel photograph.  
> Back = a visual memory derived from that photograph.

Use the established design consistently. Do not introduce stylistic variation unless the user explicitly asks for it.

## Core workflow

For each source photograph:

1. Inspect the original image and lock its orientation.
2. Read `references/photo-processing.md`.
3. Enhance the photograph naturally.
4. Crop to the required postcard ratio without changing orientation.
5. Resolve the city name and greeting.
6. Read `references/front-design.md` and `references/greetings.md`.
7. Generate the front.
8. Read `references/back-design.md`.
9. Select 1–3 visual-memory elements from the source/front.
10. Generate the back.
11. Run the mandatory QA checks below.
12. Return the requested output files.

For a compact execution checklist, read `references/operational-workflow.md`.

## Hard orientation rule

Determine orientation from the ORIGINAL uploaded photograph.

```text
original width > original height
→ landscape
→ front 1536 × 1024
→ back 1536 × 1024

original height > original width
→ portrait
→ front 1024 × 1536
→ back 1024 × 1536
```

Never rotate or reinterpret the orientation because another composition seems more convenient.

Front and back must always match.

When the user says “3:2”, interpret it by orientation:

- portrait → 1024 × 1536
- landscape → 1536 × 1024

## Minimum input

Required:

- one usable photograph.

Preferred:

- city name.

If the city is explicitly supplied, use it.

If it is already clearly established in the current conversation, reuse it.

If the city is uncertain and needed for the front, ask only:

> 这张照片对应哪个城市？我会用它生成正面的城市名和当地问候语。

Do not ask the user to choose fonts, margins, divider style, postage layout, or orientation unless they explicitly want to customize the established system.

## Photo preparation

Before design:

- preserve the source image content;
- improve exposure, highlights, shadows, white balance, clarity and noise only when useful;
- keep a natural travel-photography look;
- protect landmarks, towers, domes, statue heads, animal subjects, horizons and other defining elements during cropping.

Do not use heavy HDR, aggressive saturation, synthetic color grading, or arbitrary object changes.

Follow `references/photo-processing.md`.

## Front

Follow `references/front-design.md`.

Hard front rules:

- clean white background;
- consistent white margin;
- photo has sharp 90° corners;
- no rounded corners;
- no outer photo frame;
- no drop shadow;
- uppercase deep-navy serif city name;
- fixed thin warm-gold divider with centered geometric ornament;
- smaller uppercase blue local greeting.

The divider must remain consistent across the entire postcard series.

## Greeting priority

Use this order:

1. explicit user-provided greeting;
2. previously approved greeting for the same postcard;
3. `references/greetings.md`;
4. a widely recognized local greeting only if highly certain;
5. ask the user.

Do not change an already approved city label or greeting during an unrelated correction.

## Visual-memory extraction

The back must relate to the front without reproducing the full front photograph.

Select 1–3 source elements with strong:

- place recognizability;
- silhouette;
- visual simplicity;
- memory value;
- suitability for line drawing.

Possible elements include:

- façade;
- tower;
- dome;
- arch;
- sculpture;
- bridge;
- canal;
- coastline;
- mountain;
- skyline;
- roofline;
- shell;
- animal;
- concert venue.

Do not invent a famous city landmark that is not present in the user's source image.

## Back

Follow `references/back-design.md`.

Hard back rules:

- same orientation as front;
- warm ivory / cream paper;
- subtle paper texture;
- muted blue-gray fine-line memory illustration;
- illustration normally anchored toward lower-left;
- exactly 6 separate square postcode boxes at top-left;
- exactly 1 empty dotted/dashed stamp frame at top-right;
- exactly 4 address lines on the right/lower-right;
- no traditional center vertical divider;
- no city/country label;
- no text inside the stamp frame.

The illustration must not look like a rectangular faded copy of the complete photo.

## Batch behavior

For multiple images, process every source independently.

Do NOT force one common orientation across the batch.

Example:

```text
Photo 1 portrait
→ Front 1 portrait
→ Back 1 portrait

Photo 2 landscape
→ Front 2 landscape
→ Back 2 landscape
```

After individual QA, run a series-level consistency check:

- margins;
- typography;
- divider;
- greeting hierarchy;
- paper tone;
- stamp-frame size;
- postcode-box style;
- four address lines;
- illustration strength.

## Revision behavior

When correcting an existing postcard:

1. identify the requested defect;
2. identify and lock everything already correct;
3. change only what is necessary;
4. rerun QA.

Examples:

### “背面的线稍微深一点”

Adjust only the relevant line visibility unless another defect is explicitly mentioned.

### “这张要改回竖版”

Restore portrait orientation and 1024 × 1536 for the affected side(s). Preserve all other approved design choices.

### “正面也要一起改”

Correct both sides while preserving the pair relationship.

General rule:

> Fix the requested defect; do not re-randomize the design.

## Output naming

Single postcard:

```text
<city>-front.png
<city>-back.png
```

Multiple images from one city:

```text
<city>-01-front.png
<city>-01-back.png
<city>-02-front.png
<city>-02-back.png
```

Use lowercase ASCII-safe filenames when practical.

Do not overwrite another postcard in batch mode.

## Output contract

For a normal complete postcard request, return:

1. one front image;
2. one back image.

Do not silently omit either side.

Do not merge front and back unless the user requests a contact sheet or print sheet.

If the user explicitly asks for front only or back only, return only that side.

## Mandatory QA

Before final delivery, confirm:

### Orientation and size

- [ ] Original orientation was determined before generation.
- [ ] Portrait source remains portrait.
- [ ] Landscape source remains landscape.
- [ ] Front and back orientations match.
- [ ] Portrait output is 1024 × 1536.
- [ ] Landscape output is 1536 × 1024.

### Front

- [ ] Principal subject remains intact.
- [ ] Important landmark structure is not accidentally cropped.
- [ ] Photo corners are 90°.
- [ ] No photo frame.
- [ ] No rounded corners.
- [ ] No drop shadow.
- [ ] White margins are consistent.
- [ ] City name is correct.
- [ ] Greeting is correct.
- [ ] Navy serif city style is preserved.
- [ ] Gold divider is the established fixed design.
- [ ] Greeting uses the established smaller blue style.
- [ ] Text is centered and unclipped.

### Back

- [ ] Warm ivory background.
- [ ] Illustration comes from the source/front.
- [ ] Illustration is not a full faded copy of the front.
- [ ] Illustration is muted blue-gray line art.
- [ ] Illustration is subtle but visible.
- [ ] Exactly 6 postcode boxes.
- [ ] Boxes are separate squares.
- [ ] Stamp frame is empty.
- [ ] Stamp-frame style and size are consistent.
- [ ] Exactly 4 address lines.
- [ ] No center divider.
- [ ] No city/country label.

If any hard rule fails, correct or regenerate the affected side before returning it.

## User-facing response

Keep completion messages concise.

Example:

> 已按原图方向生成好正面和背面。

For corrections, mention the corrected property briefly:

> 这次已保持原来的横版，并统一为 1536×1024。

Do not repeat the entire design specification after every generation.

## Further references

Read as needed:

- `references/photo-processing.md`
- `references/front-design.md`
- `references/back-design.md`
- `references/greetings.md`
- `references/operational-workflow.md`
- `references/usage-examples.md`

`references/github-publishing.md` is for maintainers preparing the repository for public release.
