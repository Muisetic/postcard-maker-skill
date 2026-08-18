# Photo Processing Rules

## 1. Analyze before editing

Inspect the original image before enhancement or crop:

- width and height
- original orientation
- main subject
- landmark/architecture
- horizon
- important foreground elements
- exposure
- highlights and shadows
- white balance
- saturation
- noise
- perspective distortion
- areas that must not be cropped

## 2. Orientation is fixed

```text
width > height → landscape → 1536 × 1024
height > width → portrait  → 1024 × 1536
```

Never rotate portrait into landscape or landscape into portrait simply for convenience.

## 3. Enhancement goal

Create polished but natural travel photography.

Allowed when useful:

- exposure correction
- highlight recovery
- shadow recovery
- white balance
- subtle contrast
- subtle clarity
- gentle dehazing
- gentle sharpening
- noise reduction
- minor horizon correction
- minor perspective correction

Avoid:

- heavy HDR
- oversaturation
- synthetic color grading
- adding new objects
- removing meaningful architecture
- flattening all shadows
- aggressive sharpening

## 4. Smart crop priority

1. preserve the principal subject
2. preserve landmark identity
3. preserve architectural tops and important edges
4. preserve meaningful foreground objects
5. preserve a natural horizon
6. maintain visual balance
7. remove expendable peripheral areas last

Never use blind center-cropping when it damages the subject.

## 5. Crop QA

- [ ] original orientation preserved
- [ ] final ratio correct
- [ ] principal subject intact
- [ ] landmark recognizable
- [ ] no important structure clipped
- [ ] horizon natural
- [ ] enhancement remains believable
