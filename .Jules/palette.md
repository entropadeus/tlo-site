## 2024-05-22 - Skip Link Focus Management
**Learning:** Native focus behavior for skip links is fragile. Simply setting `href="#main"` isn't enough; the target container must have `tabindex="-1"` to accept programmatic focus, otherwise focus often stays on the link or resets to body. Additionally, global smooth-scroll scripts will hijack the jump unless explicitly excluded.
**Action:** Always add `tabindex="-1"` to skip link targets and exclude `.skip-link` class from any global anchor click listeners.
