# Palette's Journal

## 2025-02-12 - Skip Link & Smooth Scroll Interaction
**Learning:** Native "Skip to Content" links break if a global smooth-scroll script intercepts all `a[href^="#"]` clicks. The native browser behavior (jumping + moving focus) is often prevented by `e.preventDefault()`.
**Action:** Always exclude `.skip-link` from global smooth scroll selectors (e.g., `a[href^="#"]:not(.skip-link)`) to ensure accessibility features work as intended.

## 2025-02-12 - Z-Index Wars
**Learning:** Sticky headers often have high z-indices (e.g., 1000). Accessibility overlays like Skip Links must explicitly exceed this (e.g., 2001) to be visible when focused.
**Action:** Check the computed z-index of the header before adding fixed position accessibility helpers.
