# DATA_SCHEMA.md — Wellbe Study IA

**Versión:** 1.0 · **Última actualización:** 2026-05-05

---

## 1. `config.json`

Configuración general de la aplicación: niveles, dominios, privacy y mensajes de Wellbe.

### Campos principales

| Campo | Tipo | Descripción |
|-------|------|-------------|
| `app_name` | String | "Wellbe Study IA" |
| `version` | String | Semver de la app |
| `storage_key` | String | Clave de localStorage para progreso |
| `profile_key` | String | Clave de localStorage para perfil |
| `mission` | String | Misión de la app (mostrada en pantalla principal) |
| `levels` | [Level] | Definición de los 4 niveles |
| `wellbe` | Object | Configuración del mentor Wellbe |
| `privacy` | Object | Compromisos de privacidad |
| `content_boundaries` | [String] | Límites de contenido |
| `domains` | [Domain] | Dominios temáticos de los casos |

### Tipo `Level`

| Campo | Tipo | Descripción |
|-------|------|-------------|
| `level` | Number | 1, 2, 3 o 4 |
| `label` | String | Etiqueta: "N1 · Modo Claro" |
| `min_points` | Number | Puntos mínimos para alcanzar el nivel |
| `color` | String | Color hex del nivel |
| `wellbe_message` | String | Mensaje de Wellbe para este nivel |

### Tipo `Domain`

| Campo | Tipo | Descripción |
|-------|------|-------------|
| `id` | String | Identificador: `meta-wellbe`, `nutricion-comunicacion`, etc. |
| `name` | String | Nombre del dominio |
| `icon` | String | Emoji del dominio |
| `desc` | String | Descripción breve |

### Dominios registrados

`meta-wellbe` · `nutricion-comunicacion` · `justicia-alimentaria` · `salud-publica` · `ia-responsable` · `institucional`

---

## 2. `cases.json`

Array de 12 casos de estudio. Este es el archivo más complejo.

### Tipo `Case`

| Campo | Tipo | Req | Descripción |
|-------|------|-----|-------------|
| `id` | String | ✅ | Patrón: `case-n{nivel}-{nn}`. Ej: `case-n1-01` |
| `level` | String | ✅ | "N1", "N2", "N3" o "N4" |
| `order` | Number | ✅ | Orden global (1–12) |
| `title` | String | ✅ | Título del caso (máx 50 chars) |
| `type` | String | ✅ | Tipo de actividad (ver tabla) |
| `domain` | String | ✅ | ID del dominio temático |
| `points` | Number | ✅ | Puntos al completar |
| `estimated_minutes` | Number | ✅ | Tiempo estimado |
| `story` | String | ✅ | Contexto narrativo del caso (quién, dónde, qué problema) |
| `objective` | String | ✅ | Qué debe demostrar el usuario |
| `wellbe_hint` | String | ✅ | Mensaje del mentor Wellbe |
| `scaffolding` | Scaffolding | ✅ | Andamiaje del caso |
| `model_answer` | ModelAnswer | ✅ | Prompt modelo y análisis |
| `wellbe_principle` | String | ✅ | Principio ético principal del caso |
| `safety_note` | String | ✅ | Nota de seguridad / derivación |
| `quiz` | Quiz | ☐ | Solo en `prompt_builder` |
| `claims` | [Claim] | ☐ | Solo en `claim_audit` |
| `ethics_scenarios` | [EthicsScenario] | ☐ | Solo en `ethics_review` |
| `evaluation_criteria` | [String] | ☐ | Para `case_simulation`, `evidence_matrix`, `policy_design` |

### Tipos de caso

| Tipo | Interacción | Niveles |
|------|-------------|---------|
| `prompt_builder` | Quiz + prompt modelo revelable | N1, N2 |
| `claim_audit` | Clasificar claims (verdadero/engañoso/sin respaldo) | N1, N2 |
| `case_simulation` | Textarea libre + criterios + modelo | N2, N3 |
| `evidence_matrix` | Textarea libre + modelo con sabe/sugiere/no sabe | N3 |
| `policy_design` | Textarea libre + modelo extenso | N4 |
| `ethics_review` | Clasificar escenarios (correcto/violación) | N3, N4 |

### Tipo `Scaffolding`

| Campo | Tipo | Descripción |
|-------|------|-------------|
| `level` | String | "alta", "media", "baja" o "ninguna" |
| `given_prompt` | String/null | Prompt completo dado al usuario (N1) |
| `fill_in_blank` | String/null | Prompt con blancos para completar (N2) |
| `hints` | [String] | Pistas contextuales (N1–N3) |

### Tipo `ModelAnswer`

| Campo | Tipo | Descripción |
|-------|------|-------------|
| `ideal_prompt` | String | Prompt modelo completo |
| `prompt_analysis` | String | Análisis de por qué el prompt es efectivo |
| `wellbe_response` | String | Respuesta simulada de Wellbe al prompt modelo |
| `verdict` | String | Veredicto para casos de ética/claims |
| `reasoning` | String | Razonamiento del veredicto |
| `evidence_summary` | Object | `{established, suggested, unknown}` para matrices |
| `source` | String | Fuentes citadas |

### Tipo `Quiz` (dentro de Case)

```json
{
  "questions": [
    {
      "q": "Enunciado de la pregunta",
      "opts": ["Opción A", "Opción B", "Opción C", "Opción D"],
      "ok": 1,
      "fb": "Feedback si acierta",
      "wfb": "Feedback si falla"
    }
  ]
}
```

### Tipo `Claim`

```json
{
  "text": "Texto del claim entrecomillado",
  "verdict": "true" | "misleading" | "false",
  "explanation": "Explicación del veredicto"
}
```

### Tipo `EthicsScenario`

```json
{
  "action": "Descripción de la acción evaluada",
  "violation": true | false,
  "principle": "Principio ético involucrado",
  "explanation": "Por qué es o no es una violación"
}
```

---

## 3. `badges.json`

Array de 6 badges.

### Tipo `Badge`

| Campo | Tipo | Req | Descripción |
|-------|------|-----|-------------|
| `id` | String | ✅ | Patrón: `badge-{slug}` |
| `name` | String | ✅ | Nombre (máx 30 chars) |
| `icon` | String | ✅ | Emoji |
| `description` | String | ✅ | Cómo ganarlo |
| `category` | String | ✅ | Categoría temática |
| `trigger` | String | ✅ | Criterio de evaluación (ver tabla) |
| `trigger_label` | String | ✅ | Descripción del criterio para UI |
| `wellbe_principle` | String | ✅ | Principio ético vinculado |

### Triggers registrados

| Trigger | Evaluación |
|---------|------------|
| `complete_first_case` | `completedIds` incluye `case-n1-01` |
| `complete_claim_audits` | 2+ casos tipo `claim_audit` completados |
| `complete_n2` | 3 casos de nivel N2 completados |
| `complete_evidence_matrices` | 2+ casos tipo `evidence_matrix` completados |
| `complete_ethics_reviews` | 2+ casos tipo `ethics_review` completados |
| `complete_n4` | 3 casos de nivel N4 completados |

---

## 4. Principios éticos válidos

`veracidad` · `prudencia` · `justicia_alimentaria` · `equidad_cultural` · `responsabilidad_informacional` · `confidencialidad` · `comunicacion_no_estigmatizante` · `supervision_humana`

---

## 5. Reglas de validación

```
CASO NUEVO
[ ] id único y sigue patrón case-n{N}-{NN}
[ ] level es N1, N2, N3 o N4
[ ] type es un tipo registrado
[ ] domain existe en config.json
[ ] points: N1=150, N2=200, N3=300, N4=400
[ ] story describe quién, dónde y qué problema
[ ] scaffolding.level corresponde al nivel del caso
[ ] model_answer incluye prompt ideal y análisis
[ ] wellbe_principle es un principio válido
[ ] safety_note menciona derivación a RDN cuando aplica
[ ] Si type=prompt_builder → quiz requerido
[ ] Si type=claim_audit → claims[] requerido
[ ] Si type=ethics_review → ethics_scenarios[] requerido
[ ] Si type=case_simulation/evidence_matrix/policy_design → evaluation_criteria[] requerido
```

---

*Documento mantenido por el equipo de Wellbe Study IA.*
