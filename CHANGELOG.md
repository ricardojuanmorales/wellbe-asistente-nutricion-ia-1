# CHANGELOG.md — Wellbe Study IA

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
