# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Static company homepage for Frontside Solutions B.V., served by GitHub Pages at https://front-side-solutions.com/ from the `main` branch of `Matros1975/front-side-solutions`. Pushing to `main` republishes the site; there is no build step, package manager, linter or test suite.

Preview locally with `python3 -m http.server` (then open http://localhost:8000) or by opening `index.html` directly.

## Structure

- `index.html` — the entire site: markup plus all CSS in one inline `<style>` block. No JavaScript. Only external dependency is the Schibsted Grotesk font from Google Fonts.
- `img/` — founder portrait as WebP (`andrei-440`/`andrei-710` srcset, `andrei-face` avatar) plus `andrei-og.jpg` for social previews. Generated from the original photo with `cwebp -metadata icc` so camera/EXIF metadata is stripped; keep it that way for any new image.
- `CNAME` — custom domain for GitHub Pages. Removing or changing it breaks the domain.
- `.nojekyll` — disables Jekyll processing on Pages; keep it.

## Conventions

- Company name is spelled **Frontside Solutions B.V.** (one word) in all copy; the domain is `front-side-solutions.com` (hyphenated). Don't "fix" either to match the other.
- Colors are OKLCH custom properties on `:root` with dark-mode overrides under `@media (prefers-color-scheme:dark)`. Deep pine-teal (`--deep`) frames the hero and contact bands; copper (`--copper`) is the single highlight, echoing the brick in the portrait. Add new colors as tokens rather than hard-coding values.
- CSS is written minified (one rule per line, no spaces). Match that style.
- Layout max width `72rem`. Breakpoints: `44rem` (service rows go two-column), `46rem` (hero splits text | portrait), `56rem` (services heading becomes a sticky side column, contact splits).
- Load motion is CSS-only keyframes inside `prefers-reduced-motion:no-preference`.
- Footer carries legal details (KvK number 85332003, copyright year) and a link to the HopFocus product subdomain.
