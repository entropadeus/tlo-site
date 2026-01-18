# Palette's Journal

## 2024-05-21 - Accessible Skip Links & Smooth Scroll Interaction
**Learning:** Native `scroll-padding-top` handles fixed header offsets elegantly for standard anchors, but custom smooth-scroll scripts can hijack focus management.
**Action:** When implementing skip links (`.skip-link`), always explicitly exclude them from global smooth-scroll selectors (e.g., `a[href^='#']:not(.skip-link)`) to preserve the browser's native immediate jump and focus behavior.
