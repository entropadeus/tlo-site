## 2024-05-22 - Smooth Scroll vs. Accessibility Anchors
**Learning:** The custom smooth scroll implementation (`document.querySelectorAll('a[href^="#"]')`) hijacked click events for all anchor links, including the "Skip to main content" link. This prevented the browser's native focus management from moving focus to the target ID (`#main-content`), rendering the skip link ineffective despite being visually present.
**Action:** Always exclude accessibility-specific anchors (like `.skip-link`) from global smooth scroll selectors using `:not(.skip-link)` to preserve native focus behavior.
