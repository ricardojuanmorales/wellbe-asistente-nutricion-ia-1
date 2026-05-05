# Testing and Validation

## Technical Checks

- `index.html` loads without external scripts, fonts, or APIs.
- All files in `data/` contain valid JSON.
- Every `route.activity_ids` value exists in `activities.json`.
- Every `route.badge_ids` value exists in `badges.json`.
- `game_config.default_avatar_id` exists in `avatars.json`.
- The page is usable on mobile and desktop widths.

## Manual UX Validation

Ask testers to complete these tasks:

- Explain what Wellbe Quest is after seeing the first screen.
- Identify one route they would try.
- Identify one activity that feels easy to complete.
- Describe whether badges feel supportive or pressuring.
- Describe whether any content feels too clinical, vague, or uncomfortable.

## Success Signals

- Users understand the quest metaphor without coaching.
- Users can name the next action they would take.
- Users describe activities as gentle and approachable.
- Users do not confuse the product with therapy or medical care.

## Risks to Watch

- Gamification that creates pressure instead of support.
- Prompts that accidentally request sensitive information.
- Content that sounds diagnostic or prescriptive.
- Local JSON fetch failures when opening the file directly instead of through a static server.
