## 2025-12-17 - Low Contrast Accent Color
**Learning:** The design system uses `--color-accent` (#C9A227) for text elements like `.eyebrow` and links, but it fails WCAG AA contrast requirements against the light background (ratio ~1.6:1).
**Action:** Future improvements should introduce a darker variant (e.g., `--color-accent-text`) or enforce usage of `--color-accent-dark` for all text elements to ensure readability.
