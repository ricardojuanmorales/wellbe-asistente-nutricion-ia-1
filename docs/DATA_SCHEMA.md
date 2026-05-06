# DATA_SCHEMA.md — WellBe Asistente v0.1.0

Esquemas de los archivos JSON en `/data/`. Editables con cualquier editor de texto.

---

## routes.json

```json
{
  "id": "route-ia-responsable",
  "title": "IA Responsable",
  "short_title": "IA Responsable",
  "domain": "inteligencia artificial y ética",
  "story": "Narrativa de la ruta",
  "learning_goal": "Objetivo de aprendizaje",
  "level": "inicial | intermedio",
  "estimated_minutes": 34,
  "color": "#4f46e5",
  "activity_ids": ["act-ia-quiz-1", "act-ia-mindmap-1"],
  "badge_ids": ["badge-etico-ia"]
}
```

---

## activities.json — campos comunes

```json
{
  "id": "act-ia-quiz-1",
  "route_id": "route-ia-responsable",
  "title": "Título de la actividad",
  "type": "quiz | claim_detector | branching_case | mind_map | simple_simulation | reflection | lectura | reto",
  "story": "Contexto narrativo breve",
  "objective": "Objetivo de aprendizaje",
  "points": 25,
  "estimated_minutes": 10,
  "suggested_level": "Nivel 1",
  "educational_boundary": "Aviso sobre límites educativos",
  "wellbe_hint": "Mensaje del asistente (opcional)",
  "content": { }
}
```

### Tipo: `quiz`
```json
"content": {
  "questions": [
    {
      "id": "q1",
      "text": "Pregunta",
      "options": [
        { "id": "a", "text": "Opción A" },
        { "id": "b", "text": "Opción B" }
      ],
      "correct": "b",
      "explanation": "Explicación de la respuesta correcta"
    }
  ]
}
```

### Tipo: `claim_detector`
```json
"content": {
  "intro": "Instrucciones iniciales",
  "claims": [
    {
      "id": "c1",
      "text": "La afirmación a evaluar",
      "verdict": "true | misleading | false",
      "explanation": "Explicación del veredicto"
    }
  ]
}
```

### Tipo: `branching_case`
```json
"content": {
  "scenario": "Descripción del escenario",
  "start": "inicio",
  "steps": {
    "inicio": {
      "text": "Texto del paso",
      "choices": [
        { "text": "Opción A", "next": "paso-a" },
        { "text": "Opción B", "next": "paso-b" }
      ]
    },
    "paso-a": {
      "text": "Texto del siguiente paso",
      "is_end": true,
      "wellbe_closing": "Mensaje de cierre de WellBe"
    }
  }
}
```

### Tipo: `mind_map`
```json
"content": {
  "center": "Concepto central",
  "reflection": "Pregunta de reflexión al final",
  "nodes": [
    {
      "id": "n1",
      "label": "Etiqueta del nodo",
      "color": "#4f46e5",
      "description": "Descripción del nodo",
      "examples": ["Ejemplo 1", "Ejemplo 2"]
    }
  ]
}
```

### Tipo: `simple_simulation`
```json
"content": {
  "intro": "Introducción a la simulación",
  "reflection": "Pregunta de reflexión final",
  "steps": [
    {
      "id": "s1",
      "label": "Etiqueta del paso",
      "description": "Contexto del paso",
      "question": "Pregunta de decisión",
      "options": [
        {
          "id": "a",
          "text": "Opción de decisión",
          "effect": "Consecuencia mostrada al usuario",
          "resilience_change": 2
        }
      ]
    }
  ]
}
```

### Tipo: `reflection`
```json
"content": {
  "wellbe_message": "Mensaje introductorio de WellBe (opcional)",
  "prompts": [
    { "id": "p1", "text": "Pregunta de reflexión" }
  ]
}
```

### Tipo: `lectura` *(nuevo en v0.1)*
```json
"content": {
  "text": "Texto formativo (2-4 párrafos). Usar \\n\\n para separar párrafos.",
  "questions": [
    {
      "id": "q1",
      "text": "Pregunta de comprensión",
      "options": [
        { "id": "a", "text": "Opción A" },
        { "id": "b", "text": "Opción B" },
        { "id": "c", "text": "Opción C" }
      ],
      "correct": "b",
      "explanation": "Explicación de la respuesta correcta"
    }
  ]
}
```

### Tipo: `reto` *(nuevo en v0.1)*
```json
"content": {
  "intro": "Contexto o motivación del reto",
  "challenge": "Descripción concreta del reto a realizar",
  "steps": [
    { "id": "paso1", "text": "Descripción del paso a marcar" }
  ],
  "wellbe_closing": "Mensaje de cierre cuando se completan todos los pasos"
}
```

---

## badges.json

```json
{
  "id": "badge-primer-paso",
  "name": "Nombre del badge",
  "description": "Descripción de por qué se gana",
  "category": "inicio | avance | constancia | maestria | tecnologia | accion",
  "trigger": "complete_1_activity | complete_1_route | complete_6_activities | complete_12_activities | complete_ia_route | complete_reto",
  "trigger_label": "Descripción legible del trigger"
}
```

---

## avatars.json

```json
{
  "id": "avatar-indigo",
  "name": "Índigo",
  "role": "Descripción del rol",
  "description": "Descripción del avatar",
  "traits": ["rasgo1", "rasgo2", "rasgo3"]
}
```

---

## game_config.json (campos clave)

- `default_avatar_id`: ID del avatar seleccionado por defecto
- `levels[].min_points`: Puntos mínimos para alcanzar ese nivel
- `levels[].wellbe_message`: Mensaje que muestra WellBe al llegar al nivel
- `export_import.storage_key`: Clave de localStorage para el progreso — **no modificar sin migración**
- `privacy.commitments`: Lista de compromisos de privacidad mostrados en la interfaz
- `content_boundaries`: Límites de contenido educativo mostrados en la interfaz
