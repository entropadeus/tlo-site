## 2025-02-14 - Smooth Scroll Hijacking Skip Links
**Learning:** Custom smooth-scroll scripts that target all anchor links (`a[href^="#"]`) will intercept "Skip to content" links, preventing them from shifting focus to the main content container.
**Action:** Always exclude `.skip-link` from global smooth-scroll selectors (e.g., `:not(.skip-link)`) to preserve native browser focus behavior.
