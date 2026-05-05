# Architecture

## Current Approach

MVP V1 is a static web prototype. The browser loads `index.html`, then fetches JSON files from the local `data/` directory.

## Components

- `index.html`: Presentation layer and minimal client-side rendering logic.
- `data/routes.json`: Quest route definitions.
- `data/activities.json`: Activity catalog.
- `data/badges.json`: Badge definitions and trigger names.
- `data/avatars.json`: Avatar options.
- `data/game_config.json`: MVP configuration and safety boundaries.
- `docs/`: Product, data, validation, and ethics documentation.

## Intentional Constraints

- No backend.
- No database.
- No login or identity provider.
- No analytics.
- No external APIs.
- No package manager required.

## Future Architecture Direction

Later versions can split the app into frontend modules, add local persistence, introduce a backend API, and move content into a managed data store. Those changes should happen only after the static MVP validates core user flows.
