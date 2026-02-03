## 2025-05-22 - Skip Link vs Smooth Scroll
**Learning:** The site's global smooth-scroll script (`document.querySelectorAll('a[href^="#"]')`) captures all anchor links, preventing native focus management for accessibility links like skip-to-content.
**Action:** When adding accessibility anchors, always exclude them from the global smooth-scroll selector (e.g., `:not(.skip-link)`) or ensure the script manually handles focus transfer.
