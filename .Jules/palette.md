## 2024-05-21 - Skip Link Focus Management
**Learning:** Custom smooth-scroll scripts can hijack "Skip to content" links, preventing focus from actually shifting to the target container.
**Action:** Exclude skip links from smooth-scroll selectors (e.g., `a[href^='#']:not(.skip-link)`) and ensure the target container has `tabindex="-1"`.
