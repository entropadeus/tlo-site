# Palette's Journal

## 2024-05-22 - Initial Setup
**Learning:** This is the initial setup of the journal.
**Action:** Use this file to log critical UX/accessibility learnings.

## 2025-05-22 - Skip Link & Smooth Scroll
**Learning:** When adding a "Skip to Content" link to a site with JS-based smooth scrolling, ensure the smooth scroll script excludes the skip link (e.g., `a:not(.skip-link)`). Otherwise, the JS prevents the default anchor behavior, which is crucial for moving focus to the main content area.
**Action:** Always check for global `a[href^="#"]` listeners when implementing skip links.
