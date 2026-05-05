# Data Schema

This document describes the initial JSON shapes used by Wellbe Quest MVP V1.

## Route

```json
{
  "id": "route-grounding-001",
  "title": "Grounding Basics",
  "description": "A short route description.",
  "theme": "calm",
  "estimated_days": 3,
  "activity_ids": ["activity-breath-001"],
  "badge_ids": ["badge-first-step"]
}
```

## Activity

```json
{
  "id": "activity-breath-001",
  "title": "Three Calm Breaths",
  "type": "breathing",
  "prompt": "Take three slow breaths.",
  "estimated_minutes": 2,
  "points": 10,
  "safety_note": "Stop if the exercise feels uncomfortable."
}
```

## Badge

```json
{
  "id": "badge-first-step",
  "name": "First Step",
  "description": "Awarded after completing the first activity.",
  "category": "starter",
  "trigger": "complete_1_activity"
}
```

## Avatar

```json
{
  "id": "avatar-sprout",
  "name": "Sprout",
  "description": "A beginner-friendly avatar.",
  "traits": ["gentle", "curious", "patient"]
}
```

## Game Config

```json
{
  "app_name": "Wellbe Quest",
  "version": "MVP V1",
  "mission": "Short product mission.",
  "default_avatar_id": "avatar-sprout",
  "points": {
    "activity_completion_min": 10,
    "activity_completion_max": 20,
    "route_completion_bonus": 50
  },
  "privacy": {
    "storage": "local_only",
    "accounts_enabled": false,
    "analytics_enabled": false,
    "external_services_enabled": false
  },
  "content_boundaries": []
}
```

## ID Rules

- IDs are lowercase kebab-case.
- IDs include the content type prefix.
- Route records reference activities and badges by ID.
- V1 does not include user records or personal health data.
