# Documentation Index

This index is the starting point for anyone updating or extending the portfolio. Each section highlights the most relevant guides so you can quickly jump to the right reference before making changes.

## Content & Localization
- [config/content/README.md](config/content/README.md) — Overview of the multilingual content structure, article generation workflow, and how language-specific files are organized.
- Language JSON files (`config/content/en.json`, `config/content/de.json`, `config/content/ar.json`, `config/content/tr.json`) — Update these when editing hero, about, experience, or contact copy for a specific language.
- Inspiration articles (`config/content/inspiration/<article>/`) — Contains per-language metadata (`*.json`) and rich content (`*.html`) for the featured articles section.

## UI, Themes & Configuration
- [README.md](README.md#-theme-configuration) — Quick reference for switching themes, running the project locally, and available npm scripts.
- [CONFIG.md](CONFIG.md) — Detailed explanation of the split configuration architecture (`ui.config.json`, `content.config.json`, `language.config.json`).
- [CONFIGURATION_REORGANIZATION.md](CONFIGURATION_REORGANIZATION.md) — Background on how configuration loading works and why assets/content live under `config/`.
- `lib/themes.ts` — Source of built-in themes; extend this file when adding a new theme variant.

## Application Architecture & Requirements
- [Requirements_prompt.md](Requirements_prompt.md) — Original project requirements plus a checklist of implemented features and design goals.
- [Requirements_tabelle.md](Requirements_tabelle.md) — Tabular view of major requirements, their status, and file-level ownership.
- Component & layout configuration: review `lib/config.ts`, `lib/layoutConfig.ts`, and the `contexts/ThemeContext.tsx` implementation for how runtime configuration is wired into the UI.

## Deployment & Operations
- [DEPLOYMENT.md](DEPLOYMENT.md) — Step-by-step instructions for exporting the site to the `docs/` folder and publishing on GitHub Pages.
- `/docs/` export artifacts — Static site output consumed by GitHub Pages; ensure it is regenerated via `npm run export` before deployment.

## Change History & Project Status
- [Change_log.md](Change_log.md) — Chronological record of notable updates, responsible contributors, and affected files.
- [RECENT_UPDATES.md](RECENT_UPDATES.md) — High-level summary of the latest improvements, useful for briefing stakeholders or writing release notes.

## Getting Help
If you are unsure where to start, open an issue referencing this index and specify the section you are working on. The maintainers can point you to additional context or pair the task with subject-matter experts.
