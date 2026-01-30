# Palette's Journal

## 2025-05-21 - Skip Links & Accessibility Overlays
**Learning:** Fixed headers can obscure focused content. Accessibility overlays like "Skip to Content" links must have a z-index higher than fixed headers (at least 2000 in this project) to remain visible.
**Action:** Always verify z-index stacking context when adding overlay elements. Ensure skip targets have `tabindex="-1"` to receive programmatic focus.
