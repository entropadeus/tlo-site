# Palette's UX Journal

## 2025-02-26 - Skip Link Implementation Details
**Learning:** Adding a "Skip to main content" link requires two critical technical details often missed:
1. The target element must have `tabindex="-1"` to allow programmatic focus to actually "land" there, otherwise the next Tab press resets to the top of the page.
2. Custom smooth-scroll scripts (common in landing pages) often hijack all `href^="#"` clicks. The skip link must be explicitly excluded (e.g., `:not(.skip-link)`) to preserve the browser's native instant-jump and focus-shifting behavior.

**Action:** When implementing skip links in JS-heavy landing pages, always verify `document.activeElement` after the jump and audit global click listeners for interference.
