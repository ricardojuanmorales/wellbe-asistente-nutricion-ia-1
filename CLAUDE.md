# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project identity

**WellBe — Asistente de Aprendizaje Transdisciplinario** (`wellbe-asistente-nutricion-ia-1`)

A static, gamified learning platform exploring how AI and emerging technologies relate to public health, agroecology, nutrition, and buen vivir. No backend, no build step, no npm — the entire application is a single `index.html` that loads JSON data files via `fetch`.

## Running locally

Because `index.html` uses `fetch` for JSON data, it requires a static server (not `file://`):

```bash
python3 -m http.server 8000
# or
npx serve .
```

Open `http://localhost:8000`.

## Architecture

```
index.html          # Full app: HTML + CSS + JS (single file, no framework)
data/
  routes.json       # Learning routes (branching paths by interest)
  activities.json   # Interactive activities: quiz, reflection, challenge, etc.
  badges.json       # Badges with unlock triggers
  avatars.json      # Learner avatars (no physical appearance)
  game_config.json  # Levels, points thresholds, Wellbe messages, privacy commitments
docs/               # Architecture, data schema, privacy, roadmap
exports/            # Gitignored; for manual user exports only
```

All game logic, rendering, and state live in `index.html`. There is no transpilation, bundler, or framework.

## Data + state model

- **Progress** is stored in `localStorage` under a versioned key and exported/imported as JSON.
- `normalizeProgress()` is the canonical function for deriving state (points, badges, level, route progress) from a raw completed-activity list — always route mutations through it.
- JSON files in `data/` must remain editable by non-technical users (docentes, researchers). Use stable kebab-case IDs and keep schemas documented in `docs/DATA_SCHEMA.md`.
- Cross-references: `activities.json` → `route_id` → `routes.json`; `badges.json` → `trigger` evaluated against activity/route completion sets.

## Content and ethics constraints

- WellBe is an educational co-pilot, not a clinical tool. Avoid diagnostic, prescriptive, or blame language.
- Privacy-first defaults: no external requests, no telemetry, no personal data leaves the browser without explicit user action.
- Activity types: `quiz`, `claim_detector`, `branching_case`, `mind_map`, `simple_simulation`, `reflection`. New types require a renderer in `index.html` and schema documentation.

## Current status

Phase 0 — Initial scaffolding · Version 0.0.1 · Active development. The `index.html` is being built fresh for this project.
