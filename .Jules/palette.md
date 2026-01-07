# Palette's Journal

## 2025-05-18 - Accessibility Findings
**Learning:** The site relies heavily on inline styles within `index.html` and lacks a build process. Accessibility improvements must be made directly in this file. Key findings include missing skip links and icon-only buttons without accessible names.
**Action:** Always check for `index.html` as the source of truth in this project and ensure all interactive elements, especially icon-only buttons, have `aria-label` attributes.
