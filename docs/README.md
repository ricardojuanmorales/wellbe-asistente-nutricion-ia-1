# Wellbe Quest MVP V1

Wellbe Quest MVP V1 is a static-first prototype for a wellbeing quest experience. It uses one `index.html` file, local JSON data, and Markdown documentation. There is no backend, account system, analytics, or external service dependency in this version.

## Project Structure

```text
index.html
data/routes.json
data/activities.json
data/badges.json
data/avatars.json
data/game_config.json
docs/README.md
docs/ARCHITECTURE.md
docs/DATA_SCHEMA.md
docs/PRIVACY_ETHICS.md
docs/ROADMAP.md
docs/TESTING_VALIDATION.md
docs/USER_CASES.md
```

## MVP Goal

The goal is to validate whether users understand and value a simple quest-based wellbeing flow before investing in backend services, accounts, personalization, or integrations.

## Running Locally

Because `index.html` loads local JSON files with `fetch`, use a static file server from the project root.

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.
