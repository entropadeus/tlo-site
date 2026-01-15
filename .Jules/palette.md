# Palette's UX Journal

## 2025-05-15 - Fixed Header & Keyboard Navigation
**Learning:** Fixed headers often obscure content when using anchor links or skip links.
**Action:** Ensure `scroll-padding-top` is set on `html` to account for the fixed header height. (This site correctly uses `scroll-padding-top`).

## 2025-05-15 - Skip Links & JS Hijacking
**Learning:** Custom smooth-scroll scripts often break accessibility skip links by preventing default behavior and failing to move focus.
**Action:** Always exclude `.skip-link` from global smooth-scroll selectors (e.g. `a[href^="#"]:not(.skip-link)`) and ensure the target element has `tabindex="-1"` to receive programmatic focus.
