# CLAUDE.md

This file provides guidance for AI assistants working on the `brianlamb.github.io` repository.

## Project Overview

This is a personal GitHub Pages site for Brian Lamb (`@rocketmanblamb`). It is a minimal static HTML site served directly by GitHub Pages — no build tools, no framework, no package manager.

The project originally used [Hugo](https://gohugo.io/) as a static site generator but was later simplified to plain HTML.

## Repository Structure

```
brianlamb.github.io/
├── index.html      # Main homepage (only page)
├── README.md       # Brief project description
└── CLAUDE.md       # This file
```

**Missing file:** `index.html` references `styles.css` but that file does not yet exist in the repository. Any styling changes require creating it.

## Technology Stack

- **HTML5** — only markup language in use
- **CSS** — referenced via `styles.css` (not yet created)
- **GitHub Pages** — hosting platform; the `main` branch is served directly at `https://brianlamb.github.io`
- **No JavaScript framework, build tools, or package manager**

## Development Workflow

Because there is no build system, development is straightforward:

1. Edit files directly (HTML, CSS, etc.)
2. Preview locally by opening `index.html` in a browser, or use a simple local server:
   ```bash
   python3 -m http.server 8080
   # then open http://localhost:8080
   ```
3. Commit and push to deploy (GitHub Pages serves `main` automatically)

There are no tests, linters, or CI/CD pipelines configured. Changes go live as soon as they are merged to `main`.

## Branching Convention

- `main` — production branch, served by GitHub Pages
- `claude/<description>-<session-id>` — feature branches used by AI assistants (e.g., `claude/add-claude-documentation-XHWw2`)

When working as an AI assistant:
- Develop on the designated `claude/` branch
- Commit with clear, descriptive messages
- Push with `git push -u origin <branch-name>`
- Never push directly to `main` without explicit permission

## Conventions and Patterns

### HTML
- Use semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<footer>`)
- Include `alt` text on all images for accessibility
- Charset is `UTF-8`
- External images are loaded via absolute URLs (e.g., from GitHub CDN)

### CSS (when created)
- The stylesheet should be named `styles.css` and placed at the repository root (already referenced in `index.html`)
- No CSS framework is currently used; prefer vanilla CSS unless a framework is explicitly requested

### Git
- Commit messages should be short and imperative (e.g., `Add styles.css`, `Update footer links`)
- Keep commits focused on a single concern

## Key Facts for AI Assistants

- **No npm/yarn/pnpm** — do not run `npm install` or similar commands
- **No build step** — HTML and CSS are served as-is; no compilation needed
- **No tests** — there is no test suite to run or maintain
- **No linting** — no ESLint, Prettier, Stylelint, or similar tools are configured
- **styles.css is missing** — if styling work is requested, create this file at the repo root
- The Hugo logo and GitHub logo in the footer are loaded from external CDN URLs; they do not need to be copied locally
- Copyright year in the footer currently reads 2023 — update it when making footer changes
