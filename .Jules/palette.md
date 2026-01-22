## 2025-02-12 - Skip Links vs Smooth Scroll
**Learning:** Generic "smooth scroll" scripts that target all `a[href^="#"]` links often break accessibility skip links. They `preventDefault()` which stops the browser from moving keyboard focus to the target content.
**Action:** Always exclude `.skip-link` from smooth scroll selectors (e.g., `a[href^="#"]:not(.skip-link)`) to preserve native focus behavior.
