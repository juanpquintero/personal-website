# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website / landing page for Juan Pablo Quintero (backend, cloud, and automation focus), built with Astro as a fully static site (no backend, no dynamic APIs). Visual identity is a warm "Gruvbox" retro-terminal theme — see [DESIGN.md](DESIGN.md) for the full brand/design spec and [ARCHITECTURE.md](ARCHITECTURE.md) for the living architecture reference (keep both in sync with structural changes; there's an `architecture-doc` skill under `.agents/skills/` that manages `ARCHITECTURE.md` updates).

Content and UI copy are in Spanish (`<html lang="es">`).

## Commands

Package manager is **pnpm** (see `pnpm-workspace.yaml` / `pnpm-lock.yaml`), even though scripts are also invocable via npm.

- `pnpm install` — install dependencies
- `pnpm dev` — start dev server at `localhost:4321`
- `pnpm build` — build static site to `./dist/`
- `pnpm preview` — preview the production build locally
- `pnpm astro check` — type-check `.astro` files (no separate lint/test scripts are configured)

There is no test suite or linter configured in this repo currently — do not assume one exists.

## Architecture

Single-page static Astro site (Astro v6, no UI framework/islands — no React/Vue/Svelte). Interactivity is implemented with plain `<script>` blocks inside `.astro` components.

- `src/pages/index.astro` — the only page; composes `Layout` + section components (`Hero`, `AboutMe`, `Ecosistema`) in order, plus two inline sections ("divulgación" and "contacto") directly in the page.
- `src/layouts/Layout.astro` — base HTML shell: imports `global.css`, sets SEO meta tags/title/description via `Props`, loads Google Fonts (JetBrains Mono + IBM Plex Sans), and renders `ZeroGravityBackground` behind the `<slot />`.
- `src/components/` — section/UI components. Each `.astro` file is self-contained: markup + `<style>` (scoped by Astro) + optional `<script>`, following the pattern of the built-in Astro starter component `Welcome.astro` (currently unused/leftover from `create-astro`, not referenced by any page).
- `src/styles/global.css` — the design system as CSS custom properties on `:root` (`--color-*`, `--font-*`, `--spacing-*`, `--rounded-*`), plus shared component classes (`.card`, `.badge`, `.button-primary`, `.terminal*`, `.zero-gravity`) reused across components. New components should consume these variables/classes rather than hardcoding colors, spacing, or radii — values must match [DESIGN.md](DESIGN.md).
- No `src/content/` collections exist yet despite being referenced in ARCHITECTURE.md as a planned area (blog/portfolio markdown) — don't assume the Content Collections API is wired up until you check.

### Notable interactive components

- `Terminal.astro` — a simulated shell embedded in the Hero section. Commands (`help`, `ls`, `cd <section>`, `whoami`, `clear`) are handled in a `switch` inside a `<script>` block; `cd <section>` smooth-scrolls to a page element by id. Re-initializes on `astro:page-load` (Astro view-transition compatible) in addition to the initial call — follow this same init pattern for any new client-side script so it survives Astro navigation. User input is HTML-escaped via `escapeHTML()` before being echoed back — preserve this when touching terminal output to avoid XSS.
- `ZeroGravityBackground.astro` — full-viewport fixed canvas with a particle animation (`Particle` class), respects `prefers-reduced-motion` (disables itself), and also reinitializes on `astro:page-load`.

### Design system rules worth knowing when writing UI

- Only two font families: JetBrains Mono (`--font-display`, headings/UI/terminal) and IBM Plex Sans (`--font-body`, prose). Never use pure black/white — stay within the `on-surface`/`neutral` Gruvbox range.
- "Elevation" is done via the `.zero-gravity` hover effect (translateY + slight rotation + hard-edged `box-shadow`, no blur) — don't introduce soft/blurred box-shadows.
- Border radii are intentionally small (2–4px on buttons/cards); avoid rounding things heavily.
