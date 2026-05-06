# 📚 Wellbe Study IA — Ruta de Estudio Asistida por IA

> *Demuestra lo que sabes. Aprende a usar Wellbe IA paso a paso.*

Wellbe Study IA es una aplicación educativa gamificada donde pruebas tus destrezas resolviendo **casos reales** asistido por **Wellbe IA como mentor**. Aprendes nutrición, comunicación, justicia alimentaria e IA responsable — y aprendes a usar Wellbe correctamente, con prompts cada vez más complejos.

---

## ¿Qué puedes hacer aquí?

- 📋 Resolver **12 casos de estudio** que simulan escenarios reales
- 🧩 Practicar **6 tipos de actividad**: construcción de prompts, auditoría de claims, simulación de casos, matrices de evidencia, diseño de políticas y revisión ética
- 📈 Avanzar por **4 niveles** (N1 Claro → N2 Operativo → N3 Investigador → N4 Evaluador)
- 🏅 Ganar **6 badges** vinculados a principios éticos de Wellbe
- 📚 Consultar **guías de usuario dentro del juego** con un clic
- 💾 Guardar tu progreso automáticamente en tu navegador
- 📤 Exportar tu progreso como JSON para guardarlo o transferirlo
- 🔒 Todo privado por defecto — tus datos no salen de tu navegador

---

## Cómo empezar (en 60 segundos)

```bash
# 1. Clona o descarga el repositorio
git clone https://github.com/ricardojuanmorales/wellbe-asistente-nutricion-ia-1.git
cd wellbe-asistente-nutricion-ia-1

# 2. Inicia un servidor local (necesario para cargar JSON)
python3 -m http.server 8000

# 3. Abre en tu navegador
# Visita http://localhost:8000
```

**¿Por qué necesito un servidor local?** Los datos viven en archivos JSON separados (`/data/`) que el navegador carga via `fetch()`. Abrir `index.html` directamente desde `file://` bloquea estas solicitudes por seguridad del navegador (CORS).

---

## Parte del ecosistema Wellbe

Wellbe Study IA es una de tres aplicaciones educativas complementarias:

| App | Enfoque | Epistemología | Wellbe IA es... |
|-----|---------|---------------|-----------------|
| **Wellbe Explore** | Exploración cultural de la comida | Constructivista — descubrimiento | Narrador / curador |
| **Wellbe Quest** | Pensamiento sistémico y buen vivir | Transdisciplinar — conexión | Co-piloto / guía |
| **Wellbe Study IA** | Praxis asistida por IA | Sociocrítica — demostración | Mentor / evaluador |

Cada app tiene identidad propia pero comparte: principios éticos de Wellbe, guardarraíles de seguridad, diseño editorial y privacidad local.

---

## Estructura del proyecto

```
wellbe-study-ia/
├── index.html                    ← SPA principal
├── data/
│   ├── config.json               ← Configuración, niveles, dominios
│   ├── cases.json                ← 12 casos de estudio
│   └── badges.json               ← 6 badges
└── docs/
    ├── README.md                 ← Este documento
    ├── ARCHITECTURE.md           ← Arquitectura técnica
    ├── DATA_SCHEMA.md            ← Esquemas de datos
    ├── WELLBE_INTEGRATION.md     ← Rol de Wellbe como mentor
    ├── PRIVACY_ETHICS.md         ← Marco ético y privacidad
    ├── ROADMAP.md                ← Plan de desarrollo
    ├── CHANGELOG.md              ← Historial de versiones
    ├── CONTRIBUTING.md           ← Cómo contribuir casos nuevos
    └── guias-usuario/
        ├── GUIA_INICIO_RAPIDO.md
        ├── GUIA_N1_BASICO.md
        ├── GUIA_N2_OPERATIVO.md
        ├── GUIA_N3_INVESTIGADOR.md
        ├── GUIA_N4_EVALUADOR.md
        ├── GUIA_PROMPTS_WELLBE.md
        ├── GUIA_DOCENTE.md
        └── SEMAFORO_RIESGO.md
```

---

## Los 4 niveles

| Nivel | Modo Wellbe | Andamiaje | Tú haces |
|-------|-------------|-----------|----------|
| **N1** Modo Claro | Prompts dados | Alto — Wellbe te muestra cómo | Entiendes y evalúas |
| **N2** Modo Operativo | Prompts sugeridos | Medio — Wellbe te da la estructura | Completas y creas |
| **N3** Modo Investigador | Hints mínimos | Bajo — tú construyes | Investigas y documentas |
| **N4** Modo Evaluador | Sin andamiaje | Ninguno — autonomía total | Diseñas e implementas |

Los niveles son **sugeridos, no bloqueados**. Puedes probar cualquier caso en cualquier momento.

---

## Para docentes e investigadores

El contenido educativo vive en archivos JSON legibles en `/data/`. Puedes editarlos con cualquier editor de texto sin programar. Consulta `docs/DATA_SCHEMA.md` para entender la estructura de cada archivo y `docs/CONTRIBUTING.md` para las plantillas de casos nuevos.

---

## Principios éticos integrados

Cada caso, badge y mensaje de Wellbe está vinculado a uno de los 8 principios éticos de Wellbe IA: veracidad, prudencia, justicia alimentaria, equidad cultural, responsabilidad informacional, confidencialidad, comunicación no estigmatizante y supervisión humana.

**Wellbe Study IA no diagnostica, no prescribe y no sustituye a nutricionistas-dietistas licenciados (RDN/NDTR).** Es una herramienta educativa.

---

*Wellbe · Nutrición con evidencia, cultura y cuidado.*
