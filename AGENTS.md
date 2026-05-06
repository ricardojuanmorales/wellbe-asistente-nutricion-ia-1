# AGENTS.md

Guía para agentes que trabajen en WellBe — Asistente de Aprendizaje Transdisciplinario (v0.1.0).

## Principios

- Mantener el MVP como app estática: `index.html`, JSON en `data/` y Markdown en `docs/`.
- No agregar backend, Supabase, OAuth, APIs externas, telemetría remota ni frameworks pesados.
- No instalar dependencias salvo aprobación explícita y justificación fuerte.
- Mantener la experiencia en español claro, accesible y educativo.
- Documentar cualquier cambio de esquema en `docs/DATA_SCHEMA.md`.

## Datos

- Los JSON deben seguir siendo editables por personas no técnicas (docentes, investigadores).
- Usar IDs estables en kebab-case.
- Verificar referencias cruzadas entre rutas, actividades, badges y avatares.
- No incluir datos personales reales ni exportaciones de usuarios en el repositorio.

## Tipos de actividad (8)

| Tipo | Descripción |
|---|---|
| `quiz` | Preguntas con opciones y retroalimentación por respuesta |
| `claim_detector` | Semáforo: Verdadera / Engañosa / Falsa con explicación |
| `branching_case` | Caso con decisiones ramificadas y cierre de WellBe |
| `mind_map` | Nodos explorables con descripción y ejemplos |
| `simple_simulation` | Simulación por pasos con medidor de resiliencia |
| `reflection` | Preguntas abiertas para reflexión metacognitiva |
| `lectura` | Texto formativo + preguntas de comprensión |
| `reto` | Desafío práctico con checklist de pasos |

Para agregar un nuevo tipo: añadir renderer en `index.html`, documentar el esquema en `docs/DATA_SCHEMA.md`.

## Badge triggers reconocidos

| Trigger | Condición |
|---|---|
| `complete_1_activity` | Al menos 1 actividad completada |
| `complete_1_route` | Al menos 1 ruta completada |
| `complete_6_activities` | Al menos 6 actividades completadas |
| `complete_12_activities` | Las 12 actividades completadas |
| `complete_ia_route` | Ruta `route-ia-responsable` completada |
| `complete_reto` | Al menos 1 actividad tipo `reto` completada |

## Producto y ética

- WellBe es un asistente educativo local, no terapeuta ni profesional clínico.
- Evitar lenguaje diagnóstico, prescriptivo o culpabilizante.
- Mantener privacidad local y minimización de datos como defaults.
- Storage keys: `wellbeAsistentev01Progress` y `wellbeAsistentev01Profile` (no modificar sin migración).
