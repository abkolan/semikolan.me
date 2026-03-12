# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal website (`semikolan.me`) built with [Hugo](https://gohugo.io/) using the **Zen** theme. Hugo version 0.146.0+ is required (extended version not needed).

## Common Commands

```bash
# Start local dev server with live reload
hugo server

# Build the site for production
hugo

# Build with drafts visible
hugo server -D
```

## Linting (run from `themes/zen/`)

```bash
cd themes/zen
npm install          # first time setup
npm run lint         # lint both CSS and JS
npm run lint:css     # CSS only (stylelint)
npm run lint:js      # JS only (biome)
npm run lint-project:css   # lint project-level CSS in ../../assets/css/
npm run lint-project:js    # lint project-level JS in ../../assets/js/
```

## Architecture

- **`hugo.toml`** — site configuration (baseURL, title, theme, params, menus, outputs)
- **`content/`** — Markdown content files; section structure maps to URL paths
- **`layouts/`** — custom layout overrides (take precedence over theme layouts)
- **`assets/`** — CSS/JS processed by Hugo Pipes; override theme assets here
- **`static/`** — files copied as-is to the output (images, fonts, favicons)
- **`themes/zen/`** — the Zen theme (treat as read-only; override via project-level files)

### Theme Override Pattern

To customize the theme without modifying it, mirror the path in the project root:
- Override `themes/zen/layouts/single.html` → create `layouts/single.html`
- Override `themes/zen/assets/css/_custom.css` → create `assets/css/_custom.css`

### Key Theme Files

- `themes/zen/assets/css/_custom.css` — intended for project-specific CSS overrides
- `themes/zen/assets/css/_variables.css` — CSS custom properties for colors/spacing
- `themes/zen/layouts/` — base templates (`baseof.html`, `single.html`, `list.html`, `home.html`)

### Outputs

The site is configured to output HTML, RSS, JSON feeds, and a search index (FlexSearch.js). Ensure `hugo.toml` includes the `outputs` and `outputFormats` blocks from the example config if search or feeds are needed.
