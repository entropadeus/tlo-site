## 2025-05-23 - Accessibility Foundations: Skip Links & ARIA Labels

**Learning:**
Even in a visually polished static site, fundamental accessibility patterns like "Skip to Content" links and ARIA labels for icon-only buttons can be missed. These are critical for keyboard navigation and screen reader users but are often invisible to visual QA. I discovered that while the site had `id="main-content"`, it lacked the mechanism to jump to it. Also, footer social links were completely inaccessible to screen readers.

**Action:**
When auditing a site, always start by tabbing through the interface to check for a skip link and proper focus order. Use a screen reader or simulator to verify that icon-only buttons have accessible names. For future projects, ensure these foundational elements are part of the initial HTML boilerplate.
