## 2024-10-24 - Smooth Scroll Interference
**Learning:** Custom smooth-scroll scripts often hijack all hash links, preventing proper focus transfer for accessibility skip links.
**Action:** Always exclude `.skip-link` from global smooth-scroll selectors (e.g., `a[href^='#']:not(.skip-link)`) to preserve native focus behavior.
