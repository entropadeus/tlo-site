# Palette's UX Journal

## 2025-05-15 - Mobile Menu Accessibility
**Learning:** Static site mobile menus often lack state communication (ARIA) and focus management, creating "keyboard traps" or confusing experiences for screen reader users.
**Action:** Always implement `aria-expanded`, focus management (move to menu on open, return to button on close), and Escape key support for overlays.

## 2025-05-15 - Focus Management vs. Navigation
**Learning:** When managing focus for mobile menus (returning focus to toggle button on close), be careful not to hijack focus when the user is closing the menu via a navigation link. If focus is forced back to the toggle button after a link click, the browser might scroll back to the top, undoing the navigation.
**Action:** Distinguish between "closing without selection" (Escape, backdrop) and "closing via selection" (link click). Only return focus to the trigger in the former case.
