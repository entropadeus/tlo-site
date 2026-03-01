## 2025-10-26 - Project Initialization
**Learning:** The project is a static site (HTML/CSS/JS) with no build system or package manager (no `package.json`). `CLAUDE.md` line counts were inaccurate.
**Action:** Verify file contents and lengths manually; rely on static server and manual/Playwright verification instead of npm scripts.

## 2025-10-26 - Accessible Skip Links & Smooth Scroll
**Learning:** Global smooth-scroll scripts (`a[href^="#"]`) often hijack skip links, preventing focus transfer.
**Action:** Always exclude skip links from global scroll interceptors (e.g., `:not(.skip-link)`) to preserve native focus behavior.
