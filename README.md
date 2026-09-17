# Face shape ratio profiles and landmark measurements

Reference data behind the free, browser-only face shape detector at
[faceshapehub.com](https://faceshapehub.com/) ? the four landmark measurements, the seven
target ratio profiles, and the tolerances that decide which profile a face matches.

Nothing here is a black box: the detector publishes the numbers it compares against, so
anyone can check them, copy them or argue with them.

## Files

| File | What it is |
| --- | --- |
| `data/face-shape-ratios.csv` | Seven target profiles: for each shape, the three ratios the detector compares against, plus how far a ratio may sit from the target before it stops matching. |
| `data/face-shape-measurements.csv` | The four measurements, the landmark indices each is taken between, and how each is reported. |
| `face-shape-worksheet.pdf` | The printable tape-measure worksheet, for working a face shape out by hand. |

## The seven target profiles

| Shape | length ? cheekbone | forehead ? cheekbone | jaw ? cheekbone |
| --- | --- | --- | --- |
| Oval | 1.45 | 0.86 | 0.76 |
| Round | 1.18 | 0.90 | 0.86 |
| Square | 1.22 | 0.97 | 0.95 |
| Heart | 1.42 | 1.00 | 0.70 |
| Diamond | 1.50 | 0.74 | 0.72 |
| Oblong | 1.75 | 0.88 | 0.84 |
| Triangle | 1.32 | 0.80 | 1.02 |

A ratio may sit up to 0.30 (length ? cheekbone) or 0.12 (the two width ratios) away from a
profile and still count as a match, which is why two shapes can score close together on the
same face.

## How the numbers are produced

1. A face landmark model finds 468 points on the photo, running locally in the browser. The
   photo is never uploaded.
2. Four distances are read off those points: forehead width, cheekbone width, jaw width and
   face length.
3. All four are expressed as a percentage of face length, fixed at 100 ? relative proportions
   of one photo, not millimetres or inches.
4. Three ratios follow and are compared against the seven profiles above; the closest wins.

## Limits worth keeping

- A photo has no scale reference, so no tool can give real-world millimetres or inches from a
  photo alone.
- These profiles are a styling estimate, not a medical or anatomical classification, and not a
  measurement of a real frame size.
- Pose, lighting, hair across the forehead, glasses and lens distortion all move the landmark
  points, and therefore the ratios.
- Someone can sit between two profiles.

## Citation

> Target ratio profiles and tolerances published by Face Shape Hub (faceshapehub.com/data/), retrieved [date].

No reuse licence has been chosen for these files yet; open an issue here or use the contact
page on the site if you want to republish them.
