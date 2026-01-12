## 2024-05-23 - Smooth Scroll vs. Skip Links
**Learning:** Global smooth-scroll scripts targeting `a[href^='#']` can inadvertently break accessibility skip links by preventing the native focus jump.
**Action:** Always exclude `.skip-link` from smooth scroll selectors (e.g., `a[href^='#']:not(.skip-link)`).
