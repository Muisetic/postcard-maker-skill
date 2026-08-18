# Operational Workflow

## Single image

```text
1. Confirm usable source image
2. Determine original orientation
3. Resolve city
4. Read photo-processing rules
5. Enhance naturally
6. Crop without changing orientation
7. Read front-design + greetings
8. Generate front
9. Read back-design
10. Select 1–3 visual-memory elements
11. Generate back
12. Run front QA
13. Run back QA
14. Run pair QA
15. Return requested outputs
```

## Hard invariants

```text
Portrait → 1024 × 1536
Landscape → 1536 × 1024
Same source
Same destination
Same orientation
6 postcode boxes
1 empty stamp frame
4 address lines
No center divider
```

## Correction mode

```text
identify requested defect
→ lock all correct elements
→ change only what is necessary
→ rerun QA
```

Do not re-randomize unrelated design decisions.
