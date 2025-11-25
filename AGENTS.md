# Repository Guidelines

## Project Structure & Module Organization
- `src/`: application code, components, hooks, and utilities. Co-locate feature code by domain.
- `public/` or `assets/`: static files (images, icons, fonts).
- `tests/` and/or `src/**/*.(test|spec).{js,ts,jsx,tsx}`: unit tests colocated or mirrored.
- `scripts/`: maintenance and tooling tasks; `docs/`: project notes.
- Build output: `dist/` or `build/` (ignored by Git).

## Build, Test, and Development Commands
- Install: `npm install` — install dependencies.
- Dev: `npm run dev` — start local dev server (typically http://localhost:3000).
- Build: `npm run build` — create production build to `dist/` or `build/`.
- Preview: `npm run preview` — serve the production build locally.
- Test: `npm test` — run unit tests (add `--watch` for TDD).
- Lint/Format: `npm run lint` and `npm run format` — check and auto-fix code style.

## Coding Style & Naming Conventions
- Indentation: 2 spaces; encoding UTF-8; LF line endings.
- Naming: `camelCase` for variables/functions; `PascalCase` for components/classes; `kebab-case` for non-component filenames.
- Imports: prefer absolute or path-alias imports where configured; group and sort consistently.
- Tools: ESLint + Prettier enforced via `npm run lint`/`format` and pre-commit hooks (if configured).

## Testing Guidelines
- Framework: Jest or Vitest for unit tests; Playwright/Cypress for E2E if present.
- Location: colocate tests as `*.test.ts[x]` next to source or mirror in `tests/`.
- Coverage: focus on critical paths; avoid brittle snapshots; mock external I/O.
- Run: `npm test` (use `--coverage` for a summary report).

## Commit & Pull Request Guidelines
- Commits: follow Conventional Commits (e.g., `feat: add hero section`, `fix: correct nav aria labels`). Keep scopes small.
- PRs: include description, rationale, screenshots for UI, and linked issues (e.g., `Closes #123`). Ensure CI is green and assign reviewers.

## Security & Configuration Tips
- Secrets: store in `.env.local`; never commit `.env*`. Document required keys in `README`.
- Git hygiene: ensure `.gitignore` excludes builds, logs, caches.
- Dependencies: run `npm audit` periodically and upgrade/pin critical versions.

