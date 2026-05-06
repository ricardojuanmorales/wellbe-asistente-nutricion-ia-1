# CHANGELOG.md — Wellbe Study IA

---

## [1.0.2] — 2026-05-06

### Corregido

- La caja de información del caso ahora se muestra como tarjeta centrada, más ancha y legible.
- El modal de casos ya no colapsa el área de contenido por `flex-basis: 0`.
- El cierre por clic fuera del modal ya no se activa accidentalmente desde controles internos.
- El botón "Mostrar prompt modelo" revela la tarjeta del prompt, actualiza `aria-expanded` y desplaza el scroll interno hacia el contenido mostrado.

### Verificación

- Se validó la sintaxis del JavaScript extraído de `index.html` con `node --check`.
- Se probó la app desde servidor HTTP local y Chrome headless mediante protocolo DevTools.
- Se confirmó que el modal queda abierto, centrado y que la tarjeta del prompt modelo contiene texto visible.

### Documentación

- Se actualizó `CONTINUIDAD_SESION.md` con cierre, compendio, primer de continuidad y prompt de activación alineados al estado actual.
- Se actualizó `ROADMAP.md` con el cierre 1.0.2 y próximos pasos.

### Sincronización

- Commit publicado en `origin/main`: `2e65310 Improve case modal readability`.

---

## [1.0.1] — 2026-05-06

### Corregido

- Los archivos de datos ahora viven en `data/` para coincidir con las rutas usadas por `index.html`.
- Se corrigieron los `404` al cargar `data/config.json`, `data/cases.json` y `data/badges.json` en GitHub Pages.
- Se validó que los tres JSON sean parseables y respondan correctamente por HTTP local.

### Documentación

- Se añadió `CONTINUIDAD_SESION.md` con compendio de situación, primer de continuidad y prompt de activación para retomar el proyecto.

### Sincronización

- Commit publicado en `origin/main`: `eccf52e Fix JSON data paths`.

---

## [1.0.0] — 2026-05-05

### 🎉 MVP inicial — Wellbe Study IA

### Añadido

- SPA monolito (`index.html`) — 922 líneas
- **4 niveles:** N1 Modo Claro, N2 Operativo, N3 Investigador, N4 Evaluador
- **12 casos de estudio** (3 por nivel) cubriendo 6 dominios
- **6 tipos de actividad:** prompt_builder, claim_audit, case_simulation, evidence_matrix, policy_design, ethics_review
- **6 badges** vinculados a principios éticos de Wellbe
- **Panel de documentación in-app** con 5 secciones (inicio, prompts, semáforo, principios, niveles)
- **Scaffolding visual** que muestra andamiaje alto/medio/bajo/ninguno por caso
- **Prompt modelo revelable** en cada caso con análisis de Wellbe
- Motor de quiz con feedback inmediato
- Motor de auditoría de claims (verdadero/engañoso/sin respaldo)
- Motor de revisión ética (uso correcto/violación)
- Textarea para casos abiertos con criterios de evaluación
- Filtros por nivel (Todos/N1/N2/N3/N4)
- Perfil local, export/import JSON, reinicio
- Diseño índigo académico (Playfair Display + Nunito, `#3A2F8A`, fondo `#F4F3FB`)
- **8 guías de usuario** en formato MD
- **7 documentos técnicos** (README, ARCHITECTURE, DATA_SCHEMA, WELLBE_INTEGRATION, PRIVACY_ETHICS, ROADMAP, CHANGELOG, CONTRIBUTING)

### Decisiones técnicas

| Código | Decisión |
|--------|----------|
| DA-01 | JSON externos via fetch (patrón Quest) |
| DA-02 | Niveles sugeridos, no bloqueados |
| DA-03 | Evaluación estática de prompts en V1 |
| DA-04 | Panel de documentación in-app (nuevo en ecosistema) |

### Métricas

| Métrica | Valor |
|---------|-------|
| Líneas de código (`index.html`) | 922 |
| Casos de estudio | 12 |
| Tipos de actividad | 6 |
| Badges | 6 |
| Dominios temáticos | 6 |
| Guías de usuario | 8 |
| Documentos técnicos | 8 |
| Dependencias externas | 1 (Google Fonts) |
| Requiere servidor | Sí (fetch JSON) |

---

*Mantener actualizado con cada versión.*
