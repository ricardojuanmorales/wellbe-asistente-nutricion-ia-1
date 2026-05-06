# ROADMAP.md — Wellbe Study IA

**Versión:** 1.0 · **Última actualización:** 2026-05-05

---

## Fase 1 — MVP Estático ✅

**Stack:** HTML + CSS + JS vanilla + JSON + localStorage + servidor HTTP local  
**Estado:** Completado

### Entregables

| Entregable | Estado |
|------------|--------|
| SPA (`index.html`, 922 líneas) | ✅ |
| 4 niveles (N1–N4) con ruta visual | ✅ |
| 12 casos de estudio (3 por nivel) | ✅ |
| 6 tipos de actividad interactiva | ✅ |
| 6 badges vinculados a principios | ✅ |
| Panel de documentación in-app | ✅ |
| Scaffolding visual por nivel | ✅ |
| Prompt modelo revelable en cada caso | ✅ |
| Motor de quiz, claims y ética | ✅ |
| Export/import/reset de progreso | ✅ |
| Diseño índigo académico | ✅ |
| Documentación completa | ✅ |
| 8 guías de usuario MD | ✅ |

---

## Fase 2 — API + Evaluación dinámica (3–6 meses)

### Épicas

| Épica | Descripción | Estimado |
|-------|-------------|----------|
| React/Vite | Migrar SPA a framework con componentes | 13 días |
| Supabase | Auth + persistencia + RLS | 8 días |
| Wellbe evaluador via API | Proxy Anthropic + evaluación de prompts | 10 días |
| 12 casos nuevos | Duplicar profundidad por nivel (24 total) | 8 días |
| Retrotraer docs panel a Explore/Quest | Panel lateral en las otras dos apps | 3 días |

### Evaluación dinámica de prompts (V2)

```
Usuario escribe prompt → API proxy → Anthropic API
                                        ↓
                              Wellbe en Modo Evaluador
                                        ↓
                              Puntaje (1-5) + fortalezas
                              + áreas de mejora + prompt ideal
```

---

## Fase 3 — Institucional (6–18 meses)

- Panel docente con seguimiento de estudiantes
- Trayectorias configurables por curso
- Wellbe N3/N4 conversacional completo
- API pública de investigación educativa
- Soporte multiidioma (ES + EN)
- Certificados de competencia por nivel

---

## Próximos 3 pasos

1. **Publicar en GitHub Pages** + documentar el proceso de `python3 -m http.server`
2. **Piloto con 5–10 usuarios** (mix estudiantes + docentes) — protocolo de 30 min
3. **Retrotraer panel de docs** a Wellbe Explore y Wellbe Quest

---

*Living document. Actualizar al inicio de cada fase.*
