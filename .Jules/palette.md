## 2025-12-17 - Skip Link & Focus Management
**Learning:** Custom smooth-scroll JavaScript often hijacks standard anchor behavior (`e.preventDefault()`). This breaks accessibility features like "Skip to Content" links because it prevents focus transfer.
**Action:** Always exclude `.skip-link` (and other accessibility controls) from global smooth-scroll event listeners, or ensure the custom handler explicitly moves focus to the target element (using `target.focus()`).
