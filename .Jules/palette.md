## 2024-05-23 - Smooth Scroll vs Skip Links
**Learning:** Native smooth-scroll JavaScript implementations often hijack all anchor links (a[href^='#']), unintentionally breaking accessibility features like 'skip-to-main-content' links.
**Action:** Always exclude .skip-link from smooth-scroll selectors (e.g., :not(.skip-link)) or use CSS scroll-behavior: smooth instead of JS.
