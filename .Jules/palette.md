## 2026-01-21 - Skip Link & Focus Management
**Learning:** Native `id` jumping works for visuals, but `tabindex="-1"` is critical for programmatic focus on non-interactive containers (like `<main>`). Without it, the next "Tab" press resets to the top of the page in some contexts.
**Action:** Always add `tabindex="-1"` to the target of a skip link.
