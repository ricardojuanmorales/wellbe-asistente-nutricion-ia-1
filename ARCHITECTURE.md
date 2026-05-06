# ARCHITECTURE.md — Wellbe Study IA

**Versión:** 1.0 · **Última actualización:** 2026-05-05

---

## 1. Visión general

Wellbe Study IA es una SPA educativa gamificada donde el usuario demuestra destrezas resolviendo casos reales asistido por Wellbe IA como mentor. A diferencia de Wellbe Explore (datos embebidos en HTML) y Wellbe Quest (datos en JSON externos), Study IA sigue el patrón de Quest: datos en JSON cargados via `fetch()`.

```
Principio rector: El andamiaje decrece, la autonomía crece.
```

---

## 2. Arquitectura MVP (Fase 1)

```
Navegador
  └── index.html (SPA)
        ├── CSS embebido (tokens de diseño índigo)
        ├── JS embebido (motores de juego)
        │     ├── Router (anchor-based scrolling)
        │     ├── Motor de casos (6 tipos de actividad)
        │     ├── Motor de gamificación (puntos, niveles, badges)
        │     ├── Panel de documentación in-app
        │     └── Wellbe mentor (mensaje por nivel + modelo revelable)
        └── Datos via fetch()
              ├── data/config.json   (niveles, dominios, privacy)
              ├── data/cases.json    (12 casos de estudio)
              └── data/badges.json   (6 badges)
```

**Almacenamiento:** `localStorage` con claves `wellbeStudyV1Progress` y `wellbeStudyV1Profile`
**Servidor:** Requiere HTTP server para fetch (no funciona desde `file://`)
**Despliegue:** GitHub Pages (funciona como servidor HTTP)

---

## 3. Diferencias arquitectónicas con el ecosistema

| Dimensión | Explore | Quest | Study IA |
|-----------|---------|-------|----------|
| Datos | Embebidos en HTML | JSON via fetch | JSON via fetch |
| Servidor | No necesita | Sí (fetch) | Sí (fetch) |
| Router | Hash-based | Scroll + anchor | Scroll + anchor |
| Tipos actividad | Quiz + lectura | 6 tipos | 6 tipos (diferentes) |
| Progresión | Zonas abiertas | Rutas temáticas | Niveles lineales |
| Wellbe | Panel lateral | Modal hint | Modal + scaffolding + modelo |
| Docs in-app | No (futuro) | No (futuro) | Sí ✅ (panel lateral) |

---

## 4. Motores de actividad

### 4.1 Tipos de caso

| Tipo | Motor | Evaluación | Niveles |
|------|-------|------------|---------|
| `prompt_builder` | Quiz de comprensión + prompt modelo revelable | Estática | N1, N2 |
| `claim_audit` | Clasificar claims como verdadero/engañoso/sin respaldo | Estática | N1, N2 |
| `case_simulation` | Textarea libre + criterios + prompt modelo | Comparativa | N2, N3 |
| `evidence_matrix` | Textarea libre + criterios + modelo con sabe/sugiere/no sabe | Comparativa | N3 |
| `policy_design` | Textarea libre + criterios extensos + modelo | Comparativa | N4 |
| `ethics_review` | Clasificar escenarios como correcto/violación | Estática | N3, N4 |

### 4.2 Flujo de un caso

```
1. Abrir caso (modal)
   ├── Leer historia (contexto narrativo)
   ├── Ver hint de Wellbe (mensaje del mentor)
   └── Ver scaffolding (prompt dado / sugerido / libre según nivel)

2. Interactuar
   ├── [quiz] Responder preguntas → feedback inmediato
   ├── [claims] Clasificar claims → comparar con veredicto
   ├── [ethics] Evaluar escenarios → ver principio violado
   └── [open] Escribir prompt → comparar con modelo

3. Revelar modelo (botón "Mostrar prompt modelo")
   └── Ver prompt ideal + análisis de Wellbe

4. Completar caso → ganar puntos → check badges → recalcular nivel
```

### 4.3 Motor de scaffolding

El scaffolding es el diferenciador técnico clave de Study IA. Cada caso tiene un nivel de andamiaje que dicta cuánto ve el usuario antes de actuar:

```javascript
scaffolding: {
  level: "alta" | "media" | "baja" | "ninguna",
  given_prompt: "...",      // N1: prompt completo dado
  fill_in_blank: "...",     // N2: prompt con blancos
  hints: ["...", "..."]     // N1-N3: pistas contextuales
}
```

| Nivel scaffolding | Lo que ve el usuario | Lo que hace el usuario |
|-------------------|---------------------|----------------------|
| alta (N1) | Prompt completo + hints | Lee, comprende, responde quiz |
| media (N2) | Estructura con blancos + hints | Completa los blancos |
| baja (N3) | Solo hints mínimos | Construye prompt desde cero |
| ninguna (N4) | Nada | Autonomía total |

---

## 5. Panel de documentación in-app

Implementado como panel lateral deslizable (`#docs-panel`), activado con el botón "📚 Guías" en la navegación.

**Secciones disponibles en V1:**

| Sección | Contenido |
|---------|-----------|
| Inicio rápido | Qué es Study IA, 3 formas de empezar |
| Cómo formular prompts | Anatomía del prompt, ejemplos por nivel |
| Semáforo de riesgo | 5 colores, cuándo derivar |
| 8 principios éticos | Lista con descripción breve |
| Niveles N1–N4 | Qué hace cada nivel, qué se espera del usuario |

**Nota para el ecosistema:** Esta función debe retrotraerse a Wellbe Explore y Wellbe Quest en iteraciones futuras.

---

## 6. Decisiones de arquitectura

### DA-01: JSON externos via fetch (patrón Quest)

**Decisión:** Datos en archivos JSON separados, cargados via `fetch()`.
**Razones:** Permite a docentes editar contenido sin tocar código; simetría con Quest; separación de datos y presentación.
**Trade-off:** Requiere servidor HTTP; no funciona desde `file://`.

### DA-02: Niveles sugeridos, no bloqueados

**Decisión:** Los niveles N1→N4 son sugeridos pero no bloqueados.
**Razones:** Respetar autonomía del usuario; permitir exploración libre; evitar frustración por bloqueo.
**Trade-off:** Un usuario puede saltar a N4 sin preparación; el andamiaje "ninguna" lo hará evidente.

### DA-03: Evaluación estática de prompts (V1)

**Decisión:** En V1, la evaluación del prompt del usuario es estática (comparación visual con modelo).
**Razones:** Sin costo de API; funciona offline; permite validar el UX antes de integrar API.
**Futuro (V2):** Evaluación dinámica via API de Claude con system prompt de Wellbe evaluador.

### DA-04: Panel de documentación in-app

**Decisión:** Guías de usuario accesibles como panel lateral dentro del juego.
**Razones:** La documentación debe estar donde el usuario la necesita, no en otro archivo.
**Futuro:** Retrotraer a Explore y Quest.

---

## 7. Estructura de estado

```javascript
// Progress (localStorage)
{
  version: "1.0.0",
  completedIds: ["case-n1-01", ...],  // IDs de casos completados
  points: 450,                        // Puntos totales
  level: 2,                           // Nivel calculado
  earnedBadges: ["badge-primer-prompt", ...],
  updatedAt: "2026-05-05T..."
}

// Profile (localStorage)
{
  name: "Ana",
  role: "estudiante",
  createdAt: "2026-05-05T..."
}
```

---

## 8. Puntos y niveles

| Nivel | Puntos mínimos | Acumulado posible |
|-------|----------------|-------------------|
| N1 | 0 | 450 (3 × 150) |
| N2 | 450 | 1050 (450 + 3 × 200) |
| N3 | 1050 | 1950 (1050 + 3 × 300) |
| N4 | 1950 | 3150 (1950 + 3 × 400) |

---

*Documento mantenido por el equipo de Wellbe Study IA. Actualizar con cada decisión arquitectónica significativa.*
