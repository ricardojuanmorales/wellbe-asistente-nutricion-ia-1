# Documentación del Proyecto — WellBe Asistente de Aprendizaje Transdisciplinario

**Versión:** 0.1.0 · **Estado:** Desarrollo activo · **Fase:** 0 — Andamiaje inicial

---

## Índice

1. [Descripción del proyecto](#1-descripción-del-proyecto)
2. [Objetivos educativos](#2-objetivos-educativos)
3. [Arquitectura técnica](#3-arquitectura-técnica)
4. [Estructura de archivos](#4-estructura-de-archivos)
5. [Sistema de gamificación](#5-sistema-de-gamificación)
6. [Tipos de actividad](#6-tipos-de-actividad)
7. [Contenido educativo v0.1](#7-contenido-educativo-v01)
8. [Privacidad y ética](#8-privacidad-y-ética)
9. [Cómo ejecutar el proyecto](#9-cómo-ejecutar-el-proyecto)
10. [Cómo editar contenido](#10-cómo-editar-contenido)
11. [Roadmap](#11-roadmap)
12. [Límites y advertencias](#12-límites-y-advertencias)

---

## 1. Descripción del proyecto

WellBe — Asistente de Aprendizaje Transdisciplinario es una plataforma educativa estática, lúdica y gamificada diseñada para explorar la intersección entre inteligencia artificial, salud pública, nutrición, agroecología y el concepto filosófico del Buen Vivir.

### Principios de diseño

| Principio | Descripción |
|---|---|
| **Estático** | Sin backend, sin instalación, funciona desde el navegador |
| **Local por defecto** | El progreso vive en el navegador del usuario, no en servidores externos |
| **Editable sin código** | El contenido educativo vive en archivos JSON que cualquier docente puede editar |
| **Transdisciplinario** | Cruza salud, tecnología, agroecología, filosofía y pensamiento sistémico |
| **No clínico** | Es educativo, no diagnóstico ni prescriptivo |
| **Privacidad-first** | Sin cuentas, sin telemetría, sin APIs externas |

### Público objetivo

- Estudiantes universitarios de salud, nutrición, ciencias ambientales, educación y tecnología
- Docentes e investigadores que quieran usar o adaptar el contenido
- Comunidades y organizaciones interesadas en alfabetización crítica en IA y salud pública
- Facilitadores de procesos comunitarios de aprendizaje

---

## 2. Objetivos educativos

### Competencias que desarrolla

1. **Pensamiento crítico sobre IA** — Entender qué hace y qué no hace la inteligencia artificial en contextos de salud y nutrición
2. **Alfabetización en evidencia** — Leer y evaluar críticamente información nutricional y de salud
3. **Pensamiento sistémico** — Reconocer conexiones entre alimentación, territorio, comunidad y tecnología
4. **Ética tecnológica** — Evaluar implicaciones éticas del uso de tecnología en salud pública
5. **Perspectiva del Buen Vivir** — Aplicar un marco filosófico que cuestiona el desarrollo como crecimiento económico único

### Marco pedagógico

El diseño sigue principios de aprendizaje activo, metacognición y educación para la justicia social:

- Las actividades van de lo conceptual a lo reflexivo y lo práctico
- Los casos de ramificación no tienen respuestas únicas "correctas"
- Las reflexiones invitan a conectar el aprendizaje con el contexto propio
- Los retos prácticos anclan el aprendizaje en la realidad de la persona

---

## 3. Arquitectura técnica

### Patrón: Monolito HTML estático

```
index.html  ←  datos locales  →  localStorage
    ↑
    | fetch()
    ↓
data/*.json
```

El navegador carga `index.html`, que realiza `fetch()` paralelo de los 5 archivos JSON. No hay servidor de aplicaciones, base de datos ni procesamiento backend.

### Flujo de datos

```
Init
  ↓
Promise.all([routes, activities, badges, avatars, config])
  ↓
normalizeProgress(loadProgress())  ← localStorage
  ↓
render()
  ↓
attachEvents()

Acción del usuario
  ↓
completeActivity(id)
  ↓
recalculateAndSave()
  ├→ normalizeProgress()  ← fuente de verdad: completedActivityIds
  │     ├→ calculateRouteProgress()
  │     ├→ calculateLevel()
  │     └→ evaluateBadges()
  ├→ saveProgress()  → localStorage
  └→ render()
```

### Principios de gestión de estado

- **Fuente de verdad:** El array `completedActivityIds` es el único dato que se muta directamente. Todo lo demás (puntos, nivel, badges, progreso de ruta) se deriva de él en cada save.
- **Normalización idempotente:** `normalizeProgress()` puede ejecutarse sobre cualquier input y siempre produce un estado válido. Filtra IDs desconocidos, recalcula todo desde cero.
- **Defensivo ante datos corruptos:** La importación de progreso pasa por `normalizeProgress()`, que ignora IDs que no existen en los datos actuales.

### Storage keys (no modificar sin migración)

| Key | Contenido |
|---|---|
| `wellbeAsistentev01Progress` | Progreso de actividades, puntos, badges, avatar, nivel |
| `wellbeAsistentev01Profile` | Nombre/alias, rol, consentimiento de investigación |

### Restricciones técnicas explícitas

- Sin backend ni base de datos remota
- Sin cuentas ni OAuth
- Sin Supabase ni Firebase
- Sin APIs externas ni LLMs conectados
- Sin npm, webpack ni frameworks JS
- Sin telemetría remota ni analítica de comportamiento
- Sin cookies de rastreo

---

## 4. Estructura de archivos

```
wellbe-asistente-nutricion-ia-1/
├── index.html              # Aplicación completa (HTML + CSS + JS en un archivo)
├── README.md               # Presentación del proyecto para GitHub
├── AGENTS.md               # Guía para agentes IA que trabajen en el repositorio
├── CLAUDE.md               # Guía para Claude Code
├── data/
│   ├── routes.json         # 4 rutas de aprendizaje
│   ├── activities.json     # 12 actividades interactivas (8 tipos)
│   ├── badges.json         # 6 badges con triggers
│   ├── avatars.json        # 4 avatares transdisciplinarios
│   └── game_config.json    # Configuración: niveles, puntos, privacidad, misión
├── docs/
│   ├── DOCUMENTACION.md    # Este archivo
│   ├── GUIA_USUARIO.md     # Guía de uso para usuarios finales
│   ├── DATA_SCHEMA.md      # Esquemas JSON documentados para docentes
│   ├── ARCHITECTURE.md     # Arquitectura técnica (detalle)
│   ├── PRIVACY_ETHICS.md   # Política de privacidad y ética de datos
│   └── ROADMAP.md          # Fases de desarrollo
└── exports/
    └── .gitkeep            # Carpeta para exportaciones manuales (no se versiona)
```

---

## 5. Sistema de gamificación

### Puntos

Cada actividad otorga entre 20 y 45 puntos al completarse. Los puntos se recalculan desde las actividades completadas, no se acumulan por separado.

### Niveles

| Nivel | Nombre | Puntos mínimos | Mensaje de WellBe |
|---|---|---|---|
| 1 | Explorador/a | 0 | "Elige una ruta que despierte tu curiosidad." |
| 2 | Conector/a | 80 | "Ya estás tejiendo conexiones entre saberes." |
| 3 | Analista | 180 | "Tu mirada sistémica crece." |
| 4 | Co-creador/a | 300 | "Estás listo/a para imaginar propuestas con responsabilidad." |

### Badges

| Badge | Trigger | Categoría |
|---|---|---|
| Primer paso | 1 actividad completada | inicio |
| Ruta completa | 1 ruta completada | avance |
| Mitad del camino | 6 actividades completadas | constancia |
| Aprendizaje completo | 12 actividades completadas | maestría |
| Ético/a de IA | Ruta IA Responsable completada | tecnología |
| Retador/a | 1 actividad tipo `reto` completada | acción |

### Avatares

| Avatar | Rol |
|---|---|
| Índigo | Pensador/a sistémico/a |
| Raíz | Guardián/a de la tierra |
| Dato | Analista crítico/a |
| Nexo | Puente comunidad-tecnología |

---

## 6. Tipos de actividad

La plataforma soporta 8 tipos de actividad interactiva. Todos se renderizan en el modal nativo `<dialog>` de HTML.

| Tipo | Descripción | Condición para completar |
|---|---|---|
| `quiz` | Preguntas con opciones múltiples y retroalimentación inmediata | Responder todas las preguntas |
| `claim_detector` | Semáforo: clasificar afirmaciones como Verdadera / Engañosa / Falsa | Clasificar todas las afirmaciones |
| `branching_case` | Caso con decisiones ramificadas y cierre reflexivo de WellBe | Llegar a un nodo `is_end` |
| `mind_map` | Nodos conceptuales expandibles con descripción y ejemplos | Expandir al menos 3 nodos |
| `simple_simulation` | Simulación por pasos con medidor de resiliencia que cambia según decisiones | Completar todos los pasos |
| `reflection` | Preguntas abiertas de reflexión metacognitiva | Escribir 10+ caracteres en al menos un campo |
| `lectura` | Texto formativo seguido de preguntas de comprensión | Responder todas las preguntas de comprensión |
| `reto` | Desafío práctico con checklist de pasos que el usuario marca | Marcar todos los pasos del checklist |

### Añadir un nuevo tipo de actividad

1. Definir el esquema `content` en `docs/DATA_SCHEMA.md`
2. Añadir la función `render[Tipo](container, activity)` en `index.html`
3. Añadir el caso en el `switch` de `renderActivityContent()`
4. Añadir la etiqueta en el objeto `typeLabels`
5. Si el tipo requiere un trigger de badge, añadirlo en `evaluateBadges()` y en `AGENTS.md`

---

## 7. Contenido educativo v0.1

### Rutas

| Ruta | Color | Nivel | Tiempo |
|---|---|---|---|
| IA Responsable | Índigo `#4f46e5` | Inicial | 34 min |
| Nutrición y Datos | Esmeralda `#059669` | Inicial | 32 min |
| Salud Pública Digital | Ámbar `#d97706` | Intermedio | 36 min |
| Agroecología y Buen Vivir | Teal `#0f766e` | Intermedio | 38 min |

### Actividades por ruta

**IA Responsable**
- `act-ia-quiz-1` — Quiz: ¿Qué hace realmente la IA?
- `act-ia-mindmap-1` — Mapa mental: El ecosistema de la IA en salud
- `act-ia-branching-1` — Branching: Decisión ética — el algoritmo de triaje

**Nutrición y Datos**
- `act-nut-claim-1` — Semáforo: Afirmaciones nutricionales
- `act-nut-lectura-1` — Lectura: Cómo leer evidencia nutricional
- `act-nut-reflection-1` — Reflexión: Mi relación con la información de salud

**Salud Pública Digital**
- `act-spd-sim-1` — Simulación: Respuesta a un brote
- `act-spd-reto-1` — Reto: Mapea tu acceso a salud digital
- `act-spd-quiz-1` — Quiz: Telemedicina — posibilidades y límites

**Agroecología y Buen Vivir**
- `act-agro-mindmap-1` — Mapa mental: Sistemas agroecológicos
- `act-agro-branching-1` — Branching: La oferta de la agroindustria
- `act-agro-lectura-1` — Lectura: Buen vivir — una filosofía para otro mundo

---

## 8. Privacidad y ética

### Lo que se guarda (solo en el navegador local)

- IDs de actividades completadas
- Avatar seleccionado
- Puntos, nivel y badges derivados
- Nombre/alias opcional y rol (perfil)

### Lo que NO se guarda ni transmite

- Respuestas a preguntas de reflexión
- Pasos del reto
- Datos de identificación personal
- Historial médico o nutricional
- Información de ubicación

### Compromisos de diseño

- El progreso es del usuario: puede exportarlo, importarlo y borrarlo en cualquier momento
- No hay comparaciones entre usuarios ni rankings sociales
- Los badges celebran aprendizaje, no valor personal
- El contenido evita lenguaje culpabilizante, prescriptivo o diagnóstico
- El campo de consentimiento de investigación está desactivado por defecto y no recopila datos en v0.1

### Límites clínicos

WellBe **no** es:
- Un sistema de diagnóstico médico o nutricional
- Un recomendador de tratamientos o dietas personalizadas
- Un sustituto de profesionales de salud
- Un sistema de vigilancia o monitoreo de comportamiento

---

## 9. Cómo ejecutar el proyecto

### Requisitos

- Navegador moderno (Chrome, Firefox, Safari, Edge)
- Python 3 o Node.js (para el servidor local)

### Servidor local

```bash
# Con Python 3
python3 -m http.server 8000

# Con Node.js
npx serve .
```

Luego abre `http://localhost:8000`.

> **Importante:** No abras `index.html` directamente con doble clic (`file://`). El navegador bloqueará los `fetch()` de los archivos JSON por restricciones de seguridad CORS.

### GitHub Pages

El proyecto puede publicarse directamente con GitHub Pages:

1. Ve a **Settings → Pages** en el repositorio
2. Selecciona **Source: main / root**
3. La URL quedará en `https://ricardojuanmorales.github.io/wellbe-asistente-nutricion-ia-1/`

---

## 10. Cómo editar contenido

Todo el contenido educativo vive en archivos JSON en `/data/`. Son archivos de texto plano editables con cualquier editor (VS Code, Notepad, TextEdit).

### Flujo de edición

1. Abre el archivo JSON correspondiente en un editor de texto
2. Modifica el contenido siguiendo el esquema documentado en `docs/DATA_SCHEMA.md`
3. Guarda el archivo
4. Recarga el navegador — los cambios se reflejan inmediatamente

### Archivos y qué controlan

| Archivo | Qué controla |
|---|---|
| `data/routes.json` | Títulos, narrativas y objetivos de cada ruta |
| `data/activities.json` | Preguntas, afirmaciones, casos, textos de lectura y pasos de reto |
| `data/badges.json` | Nombres, descripciones y triggers de badges |
| `data/avatars.json` | Nombres, roles y rasgos de los avatares |
| `data/game_config.json` | Misión, niveles, puntos, compromisos de privacidad |

> Ver `docs/DATA_SCHEMA.md` para la estructura completa de cada archivo.

---

## 11. Roadmap

### v0.1.0 — Andamiaje inicial (actual)

- ✅ App estática con diseño fresco (índigo + esmeralda + ámbar)
- ✅ 4 rutas de aprendizaje con contenido original
- ✅ 12 actividades en 8 tipos (incluyendo `lectura` y `reto` como tipos nuevos)
- ✅ 6 badges con triggers
- ✅ 4 avatares transdisciplinarios
- ✅ Sistema de puntos y niveles
- ✅ Exportar / importar / reiniciar progreso en JSON
- ✅ Privacidad local, sin cuentas ni servicios externos
- ✅ Documentación de arquitectura, datos y guía de usuario

### v0.2.0 — Mejoras sin servicios externos

- Filtros por ruta y tipo de actividad en la sección de actividades
- Vista de detalle por ruta
- Modo oscuro
- Mejoras de accesibilidad (ARIA, contraste, navegación por teclado)
- Más actividades de contenido revisado por pares
- Guía para facilitadores y docentes

### v0.3.0 — Preparación pedagógica

- Rúbrica de validación educativa
- Modo bilingüe (español / inglés) si el público lo requiere
- Revisión de contenido con expertos en nutrición, salud pública y agroecología
- Casos de uso documentados por perfil de usuario

### v1.0.0 — Validación y decisión

- Evaluación de impacto educativo con usuarios reales
- Decidir si se necesita backend basado en evidencia de uso
- Evaluar riesgos antes de cualquier integración de IA externa
- Definir modelo de consentimiento y retención si se introduce persistencia remota

---

## 12. Límites y advertencias

### Para usuarios

- El contenido es educativo: no reemplaza orientación clínica, nutricional ni psicológica
- Las reflexiones escritas en las actividades no se guardan en esta versión
- El progreso es local al navegador: si limpias el almacenamiento, se pierde (usa Exportar)

### Para docentes y desarrolladores

- No modificar `storage_key` en `game_config.json` sin implementar una migración
- Los IDs de actividades y rutas son estables — cambiarlos rompe el progreso existente de los usuarios
- El sistema de badges evalúa triggers en cada save; añadir un trigger nuevo requiere actualizar `evaluateBadges()` en `index.html` y `AGENTS.md`

### Para investigadores

- En v0.1 no se recopila ningún dato, incluso si el usuario activa el consentimiento de investigación
- Cualquier versión con recopilación de datos requiere definir consentimiento informado, retención, borrado y gobernanza antes de implementación
