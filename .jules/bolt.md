## 2026-01-14 - Subsampling for Average Color Calculation
**Learning:** Iterating over every single pixel in a large image to calculate average color (used for "is dark" logic) is wasteful.
**Action:** Implemented 8x subsampling (step=8) in `pixbuf_average_value`, reducing the number of checked pixels by ~64x while maintaining sufficient accuracy.
