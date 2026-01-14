## 2026-01-14 - Subsampling for Average Color Calculation
**Learning:** Iterating over every single pixel in a large image to calculate average color (used for "is dark" logic) is wasteful.
**Action:** Implemented 8x subsampling (step=8) in `pixbuf_average_value`, reducing the number of checked pixels by ~64x while maintaining sufficient accuracy.

## 2026-01-14 - String Interning (Memory)
**Learning:** String interning is a technique where strings are stored in a global table, and duplicate strings are replaced with references to the same string in the table. This can reduce memory usage by eliminating duplicate strings and can also improve performance by allowing for faster string comparison.
**Action:** Implemented string interning in `mate-desktop-item.c` using the `g_intern_string` function. This will reduce memory usage by eliminating duplicate strings and can also improve performance by allowing for faster string comparison.

## 2026-01-14 - Aggressive Cache Pruning
**Learning:** `KEEP_EXPENSIVE_CACHE_SECS` (60s) in `mate-bg.c` was causing large background images to be retained in memory even when not needed, specifically for slideshow pre-fetching.
**Action:** Reduced `KEEP_EXPENSIVE_CACHE_SECS` to 0. This forces `mate-bg` to immediately release large pixbufs after use (e.g. after creating the X root pixmap), minimizing idle RAM usage.
