# Wellbe Quest v1 — Mapa del Buen Vivir

Aplicación educativa gamificada sobre nutrición humana, seguridad alimentaria y nutricional, agroecología, comunidad, inteligencia artificial y salud pública. Desarrollada como MVP estático: un solo `index.html`, datos JSON editables y documentación Markdown.

## Qué incluye V1

- **4 rutas educativas:** Nutrición Humana, Seguridad Alimentaria, Agroecología y Comunidad, IA y Salud Pública
- **12 actividades interactivas** con seis tipos distintos:
  - `quiz` — preguntas con retroalimentación por respuesta
  - `claim_detector` — evaluación de afirmaciones nutricionales (Verdadera / Engañosa / Falsa)
  - `branching_case` — casos con decisiones ramificadas y cierres de Wellbe
  - `mind_map` — nodos explorables con descripciones y ejemplos
  - `simple_simulation` — simulación paso a paso con medidor de resiliencia
  - `reflection` — preguntas abiertas para reflexión metacognitiva
- **Wellbe** como co-piloto educativo con mensajes contextuales en cada actividad
- **Perfil local** con nombre/alias, rol y consentimiento de investigación (off por defecto)
- **4 avatares transdisciplinarios** sin base en apariencia física
- **Sistema de puntos y niveles** (4 niveles, 6 badges)
- **Progreso en localStorage** — sin cuentas ni servidores
- **Exportar / importar / borrar progreso** en JSON
- **Estadísticas locales** básicas
- **Aviso de privacidad y límites** visible en la interfaz

## Cómo ejecutar localmente

`index.html` usa `fetch` para cargar los JSON, por lo que necesitas un servidor estático:

```bash
# Python 3
python3 -m http.server 8000

# Node (si tienes npx)
npx serve .
```

Luego abre `http://localhost:8000` en tu navegador.

> No funciona abriendo `index.html` directamente como archivo (`file://`) por restricciones de CORS en `fetch`.

## Estructura de archivos

```
wellbe-quest-mvp-1/
├── index.html              # Aplicación completa (HTML + CSS + JS)
├── data/
│   ├── routes.json         # 4 rutas educativas
│   ├── activities.json     # 12 actividades con contenido interactivo
│   ├── badges.json         # 6 badges con triggers
│   ├── avatars.json        # 4 avatares transdisciplinarios
│   └── game_config.json    # Configuración de niveles, puntos y privacidad
├── docs/
│   ├── README.md           # Documentación técnica extendida
│   ├── ARCHITECTURE.md     # Arquitectura interna y escalabilidad futura
│   ├── DATA_SCHEMA.md      # Esquemas JSON documentados
│   ├── PRIVACY_ETHICS.md   # Privacidad, ética y límites clínicos
│   ├── ROADMAP.md          # V1 actual y V2 planificado
│   ├── TESTING_VALIDATION.md # Matriz de pruebas y criterios de aceptación
│   └── USER_CASES.md       # Casos de uso por perfil
├── exports/
│   └── .gitkeep            # Carpeta para exportaciones manuales
└── README.md               # Este archivo
```

## Cómo probar las funciones principales

1. **Perfil:** Al cargar la app, completa el formulario de perfil (nombre, rol). El perfil se guarda en `localStorage`.
2. **Avatar:** Desplázate a la sección Avatar y selecciona uno.
3. **Rutas:** La sección Rutas muestra las 4 rutas con barra de progreso.
4. **Actividades:** Haz clic en "Comenzar actividad" en cualquier tarjeta. Se abre un modal interactivo.
5. **Quiz:** Selecciona una respuesta por pregunta. Se muestra explicación inmediatamente. "Completar" se habilita al responder todas.
6. **Claim detector:** Evalúa cada afirmación. Se muestra el veredicto correcto con explicación.
7. **Branching case:** Navega por el caso tomando decisiones. Cada rama lleva a un cierre diferente de Wellbe.
8. **Mind map:** Expande al menos 3 nodos para habilitar "Completar".
9. **Simulación:** Elige en cada paso. El medidor de resiliencia cambia según tus decisiones.
10. **Reflexión:** Escribe al menos 10 caracteres en una caja de texto para habilitar "Completar".
11. **Puntos y badges:** Se actualizan automáticamente al completar actividades.
12. **Exportar:** Botón "Exportar progreso" descarga un `.json` con todo el progreso.
13. **Importar:** Botón "Importar JSON" valida el archivo antes de reemplazar el progreso.
14. **Reiniciar:** Botón "Reiniciar progreso" pide confirmación antes de borrar.

## Límites del MVP

- Sin backend, autenticación, ni servicios externos
- Sin telemetría remota ni analítica de comportamiento
- No ofrece diagnóstico, tratamiento ni recomendaciones clínicas personalizadas
- El progreso vive solo en el navegador donde se usa
- La simulación y el mind map son simplificaciones educativas, no modelos técnicos reales
- Los quizzes evalúan comprensión conceptual, no conocimiento clínico

## Editar contenido sin tocar el código

Docentes e investigadores pueden editar directamente los archivos JSON en `/data/`:

- `activities.json` — cambiar preguntas, opciones, afirmaciones, pasos de ramificación
- `routes.json` — modificar títulos, descripción, objetivos de aprendizaje
- `badges.json` — agregar badges (hasta 24 en V2 sin reescribir lógica)
- `game_config.json` — ajustar niveles, puntos, mensajes de Wellbe, compromisos de privacidad

Ver `docs/DATA_SCHEMA.md` para la estructura completa de cada archivo.

## Publicar en GitHub Pages

```bash
git add .
git commit -m "Deploy MVP V1"
git push origin main
```

Luego en el repositorio de GitHub: **Settings → Pages → Source: main / root**.

La URL quedará en `https://<usuario>.github.io/<repositorio>/`.

> Nota: GitHub Pages sirve archivos estáticos, así que `fetch` funciona correctamente.
