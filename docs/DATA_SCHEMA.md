# Esquema de Datos

## Route

```json
{
  "id": "route-nutricion-humana",
  "title": "Ruta 1: Nutricion humana cotidiana",
  "short_title": "Nutricion",
  "domain": "nutricion humana",
  "story": "Narrativa breve.",
  "learning_goal": "Objetivo educativo.",
  "level": "inicial",
  "estimated_minutes": 30,
  "color": "#246b4f",
  "activity_ids": ["activity-plato-diverso"],
  "badge_ids": ["badge-primer-paso"]
}
```

## Activity

```json
{
  "id": "activity-plato-diverso",
  "route_id": "route-nutricion-humana",
  "title": "El plato diverso",
  "type": "observacion",
  "story": "Contexto narrativo.",
  "objective": "Objetivo de aprendizaje.",
  "instructions": "Accion breve.",
  "reflection_prompt": "Pregunta reflexiva.",
  "points": 20,
  "estimated_minutes": 10,
  "suggested_level": "Nivel 1",
  "educational_boundary": "Limite educativo."
}
```

## Badge

```json
{
  "id": "badge-primer-paso",
  "name": "Primer paso",
  "description": "Completaste tu primera actividad.",
  "category": "inicio",
  "trigger": "complete_1_activity",
  "trigger_label": "1 actividad"
}
```

## Avatar

```json
{
  "id": "avatar-wellbe-transdisciplinario",
  "name": "Wellbe transdisciplinario",
  "role": "co-piloto principal",
  "description": "Acompana el mapa.",
  "traits": ["curioso", "cuidadoso"]
}
```

## Progress Export

```json
{
  "version": "1.0.0",
  "selectedAvatarId": "avatar-wellbe-transdisciplinario",
  "completedActivityIds": ["activity-plato-diverso"],
  "earnedBadgeIds": ["badge-primer-paso"],
  "points": 20,
  "level": 1,
  "routeProgress": {},
  "stats": {
    "completedActivities": 1,
    "completedRoutes": 0,
    "exportedCount": 0,
    "importedCount": 0
  },
  "updatedAt": "2026-05-05T00:00:00.000Z"
}
```

## Reglas

- IDs en kebab-case.
- Rutas referencian actividades y badges existentes.
- `default_avatar_id` debe existir en `avatars.json`.
- La importacion solo acepta IDs conocidos.
- No se guardan datos personales ni respuestas libres en V1.
