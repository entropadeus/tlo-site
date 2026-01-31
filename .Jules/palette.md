## 2026-01-31 - Accessibility: Skip Links & Smooth Scroll
**Learning:** Smooth scroll scripts often hijack all anchor links, breaking accessibility features like "Skip to Content" links by preventing focus transfer.
**Action:** Always exclude `.skip-link` and other utility anchors from global smooth scroll interceptors.

## 2024-05-21 - Focus Management on Non-Interactive Elements
**Learning:** Simply linking to an ID (`#main-content`) isn't enough for focus management. Non-interactive elements (like `<main>`, `<section>`, `<div>`) require `tabindex="-1"` to receive focus programmatically or via hash navigation in many browsers.
**Action:** Ensure skip-link targets always have `tabindex="-1"`.
