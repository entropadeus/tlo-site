## 2024-05-22 - Smooth Scroll vs Skip Links
**Learning:** Custom smooth scroll implementations (often `e.preventDefault()`) hijack all anchor links starting with `#`, which breaks native "Skip to content" accessibility links that rely on instant focus transfer.
**Action:** Always exclude `.skip-link` from global smooth scroll selectors (e.g., `document.querySelectorAll('a[href^="#"]:not(.skip-link)')`) to preserve accessibility.
