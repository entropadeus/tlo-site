## 2025-05-24 - Missing Skip Link
**Learning:** For sites with fixed headers and long navigational menus, a "Skip to Content" link is critical for keyboard users to avoid tabbing through the entire menu on every page load.
**Action:** Always verify the presence of a skip link in the initial audit. When adding one, ensure it is excluded from any "smooth scroll" JavaScript interceptors to preserve native browser focus behavior, and ensure the target container is programmatically focusable (`tabindex="-1"`).
