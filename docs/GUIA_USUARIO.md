# 🌱 Guía de Usuario — Wellbe Quest v1

**Mapa del Buen Vivir**
Aplicación educativa gamificada sobre nutrición, comunidad, agroecología e IA.

---

## 📋 Contenido

1. [¿Qué es Wellbe Quest?](#qué-es-wellbe-quest)
2. [Cómo empezar](#cómo-empezar)
3. [Tu perfil educativo](#tu-perfil-educativo)
4. [Elegir tu avatar](#elegir-tu-avatar)
5. [El mapa de rutas](#el-mapa-de-rutas)
6. [Tipos de actividad](#tipos-de-actividad)
7. [Wellbe, tu co-piloto](#wellbe-tu-co-piloto)
8. [Puntos, niveles y badges](#puntos-niveles-y-badges)
9. [Exportar e importar progreso](#exportar-e-importar-progreso)
10. [Privacidad y límites](#privacidad-y-límites)
11. [Preguntas frecuentes](#preguntas-frecuentes)

---

## 🗺️ ¿Qué es Wellbe Quest?

Wellbe Quest es una **experiencia educativa gamificada** que te invita a explorar cuatro grandes territorios del conocimiento:

| Ruta | Territorio |
|------|-----------|
| 🥦 Ruta 1 | Nutrición Humana |
| 🛒 Ruta 2 | Seguridad Alimentaria y Nutricional |
| 🌿 Ruta 3 | Agroecología y Comunidad |
| 🤖 Ruta 4 | IA, Salud Pública y Buen Vivir |

Cada ruta tiene **3 actividades interactivas**. Al completarlas obtienes puntos, subes de nivel y desbloqueas badges.

> ⚠️ **Importante:** Wellbe Quest es una herramienta educativa. No ofrece diagnósticos, tratamientos ni recomendaciones clínicas personalizadas.

---

## 🚀 Cómo empezar

### Opción A — Servidor local (recomendado)

```bash
# Desde la carpeta raíz del proyecto
python3 -m http.server 8000
```

Luego abre tu navegador en:
```
http://localhost:8000
```

### Opción B — GitHub Pages

Si el proyecto está publicado, simplemente abre el enlace de GitHub Pages del repositorio.

> 🔴 **No abras `index.html` directamente** como archivo (`file://`). El navegador bloqueará la carga de los datos JSON por restricciones de seguridad.

---

## 👤 Tu perfil educativo

Al entrar por primera vez verás el formulario de perfil en la parte superior.

### Campos del perfil

| Campo | Descripción | Obligatorio |
|-------|-------------|-------------|
| 📝 Nombre o alias | Cómo quieres que te llame la app | No |
| 🎓 Rol | Estudiante, docente, investigador/a, comunidad u otro | No |
| 🔬 Consentimiento de investigación | Participación opcional en investigación futura | No — **desactivado por defecto** |

### Pasos para crear tu perfil

1. Escribe tu nombre o deja el campo vacío para usar "Explorador/a"
2. Selecciona tu rol en el menú desplegable
3. Haz clic en **Crear perfil** ✅

### Editar tu perfil

Puedes cambiar tu perfil en cualquier momento:
- Ve a la sección **Perfil** (primera sección de la página)
- Haz clic en **Editar perfil**
- Modifica los datos y guarda

> 💾 El perfil se guarda automáticamente en tu navegador. No se envía a ningún servidor.

---

## 🧭 Elegir tu avatar

Desplázate hasta la sección **Avatar** en la página.

Hay **4 avatares transdisciplinarios** disponibles. Cada uno representa una forma de conectar saberes, no una apariencia física:

| Avatar | Rol | Rasgos |
|--------|-----|--------|
| 🌍 Wellbe Transdisciplinario | Co-piloto principal | Curioso, cuidadoso, crítico, comunitario |
| 🌱 Semilla | Aprendiz agroecológico/a | Observadora, paciente, territorial |
| 🧭 Brújula | Guía de salud pública | Analítica, justa, clara |
| 💡 Luz | Exploradora de IA responsable | Creativa, prudente, tecnológica |

**Para seleccionar un avatar:** haz clic sobre la tarjeta. Quedará resaltada en verde. ✅

---

## 🗺️ El mapa de rutas

La sección **Rutas** muestra las 4 rutas del mapa con:

- 📖 **Historia** — el contexto narrativo de cada territorio
- 🎯 **Objetivo de aprendizaje**
- 📊 **Barra de progreso** — se llena al completar actividades
- ⏱️ **Tiempo estimado** y nivel de dificultad

---

## 🎮 Tipos de actividad

La sección **Actividades** muestra las 12 actividades disponibles. Haz clic en **Comenzar actividad** para abrir el modal interactivo.

### 🧪 Quiz — Preguntas conceptuales

> *Ejemplo: La Fibra Invisible*

1. Lee la pregunta en pantalla
2. Haz clic en la opción que consideras correcta
3. Se muestra inmediatamente la **explicación** de la respuesta correcta
4. Responde todas las preguntas para habilitar "Completar actividad"

✅ **Pista:** No hay penalización por responder incorrectamente. Cada error muestra la respuesta correcta con su contexto.

---

### 🚦 Semáforo de Claims — Detectar afirmaciones

> *Ejemplo: El Código de la Etiqueta / Detective de Claims*

1. Lee la afirmación en cursiva
2. Haz clic en uno de los tres botones:
   - 🟢 **Verdadera** — bien sustentada por evidencia
   - 🟡 **Engañosa** — parcialmente correcta pero distorsionada
   - 🔴 **Falsa** — incorrecta o sin base
3. Se revela el **veredicto correcto** con explicación
4. Evalúa todas las afirmaciones para completar

💡 **Tip:** Muchas afirmaciones comunes sobre nutrición son engañosas, no directamente falsas. ¡Presta atención al contexto!

---

### 🌿 Decisiones ramificadas — Branching cases

> *Ejemplo: El Plato en Contexto / Decisiones con Dignidad*

1. Lee el **escenario** en la caja de contexto
2. Se te presenta una situación con dos o más opciones
3. Haz clic en la **opción que eliges**
4. Cada elección lleva a una rama diferente del caso
5. Al llegar al final de una rama, Wellbe ofrece un **cierre reflexivo** 🌱

🔄 **Nota:** No hay respuestas "correctas" fijas. El objetivo es explorar el contexto, no acertar una respuesta única.

---

### 🧠 Mapa mental — Mind map exploratorio

> *Ejemplo: Barreras del Camino / Del Suelo al Plato*

1. Observa el **nodo central** (el tema principal)
2. Haz clic en cada nodo de colores para **expandirlo**
3. Cada nodo muestra una descripción y ejemplos concretos
4. Abre al menos **3 nodos** para habilitar "Completar actividad"
5. Lee la **pregunta de reflexión** al final del mapa

🗺️ **Tip:** Intenta conectar lo que ves en el mapa con situaciones de tu contexto real.

---

### 🌱 Simulación — Huerto Resiliente

> *Ejemplo: Huerto Resiliente*

1. Lee la introducción de la simulación
2. Observa el **medidor de resiliencia** (comienza en 5/10)
3. En cada paso, lee la situación y elige una opción
4. Se muestra el **efecto** de tu decisión y el medidor cambia
5. Después de todos los pasos, aparece la reflexión final
6. Haz clic en **Completar actividad**

📊 **El medidor:** Sube si eliges prácticas agroecológicas. Baja con decisiones de menor resiliencia. No hay "Game Over": el objetivo es reflexionar sobre las consecuencias.

---

### ✍️ Reflexión — Preguntas abiertas

> *Ejemplo: Comunidad que Siembra / Datos con Cuidado*

1. Lee el **mensaje de Wellbe** para prepararte
2. Escribe tu respuesta en los **cuadros de texto**
3. Escribe al menos una respuesta de 10+ caracteres para habilitar "Completar"
4. Haz clic en **Completar actividad**

> 🔒 Tus reflexiones **no se guardan** en esta versión (V1). Solo se registra que completaste la actividad. En V2 podrán guardarse de forma local opcional.

---

## ⭐ Puntos, niveles y badges

### Puntos por actividad

Cada actividad otorga puntos al completarse:

| Nivel de actividad | Puntos aprox. |
|-------------------|--------------|
| Nivel 1 (básico) | 20–30 pts |
| Nivel 2 (intermedio) | 30–35 pts |
| Nivel 3 (avanzado) | 35–45 pts |

### Niveles

| Nivel | Nombre | Puntos necesarios |
|-------|--------|------------------|
| 1 | 🌱 Explorador inicial | 0 pts |
| 2 | 🔗 Conector de saberes | 80 pts |
| 3 | 🔍 Analista del buen vivir | 180 pts |
| 4 | 🌍 Co-creador comunitario | 300 pts |

### Badges 🏅

| Badge | Cómo se desbloquea |
|-------|-------------------|
| Primer paso | Completar 1 actividad |
| Ruta completa | Terminar todas las actividades de 1 ruta |
| Mitad del mapa | Completar 6 actividades |
| Mapa completo | Completar las 12 actividades |
| Exploración comunitaria | Completar una actividad de Agroecología |
| IA responsable | Completar una actividad de IA y Salud Pública |

---

## 💾 Exportar e importar progreso

Ve a la sección **Progreso** en la página.

### ⬇️ Exportar

1. Haz clic en **Exportar progreso**
2. Se descarga un archivo `.json` con la fecha de hoy
3. Guárdalo en un lugar seguro

El archivo contiene: actividades completadas, puntos, nivel, badges y avatar seleccionado.

### ⬆️ Importar

1. Haz clic en **Importar JSON**
2. Selecciona el archivo `.json` exportado previamente
3. La app **valida** el archivo antes de cargarlo
4. Si el archivo es válido, tu progreso se restaura

> ⚠️ Importar reemplaza el progreso actual. Solo se aceptan archivos exportados por Wellbe Quest.

### 🗑️ Reiniciar progreso

1. Haz clic en **Reiniciar progreso**
2. Aparece una confirmación — acepta para borrar
3. El progreso vuelve a cero (el perfil y el avatar no se borran)

---

## 🔒 Privacidad y límites

### Lo que esta app hace

- ✅ Guarda tu progreso localmente en el navegador (`localStorage`)
- ✅ Permite exportar e importar tus datos como JSON
- ✅ Permite borrar todos tus datos
- ✅ Usa un perfil con nombre/alias opcional

### Lo que esta app NO hace

- 🚫 No envía datos a servidores externos
- 🚫 No tiene cuentas de usuario ni autenticación
- 🚫 No usa cookies de rastreo ni telemetría remota
- 🚫 No ofrece diagnósticos de salud
- 🚫 No recomienda dietas, tratamientos ni medicamentos
- 🚫 No hace comparaciones entre usuarios
- 🚫 No activa investigación educativa por defecto

---

## ❓ Preguntas frecuentes

**¿Puedo usar la app sin crear un perfil?**
Sí. El perfil es opcional. Sin él, la app funciona con el nombre "Explorador/a".

**¿Qué pasa si cierro el navegador?**
Tu progreso se guarda automáticamente en `localStorage`. Al volver, todo estará como lo dejaste.

**¿Puedo usar la app en varios dispositivos?**
En esta versión (V1) el progreso es local a cada navegador/dispositivo. Usa la función de **exportar** para llevarlo de un dispositivo a otro.

**¿El consentimiento de investigación recopila mis datos?**
No en V1. Es un campo preparado para una futura función de investigación educativa voluntaria. Está desactivado por defecto.

**¿Puedo reiniciar una actividad ya completada?**
Sí. Cada actividad completada muestra el botón **Reiniciar** para volver a realizarla.

**¿Cómo edita el contenido un docente?**
Los archivos `data/*.json` son editables con cualquier editor de texto. Ver `docs/DATA_SCHEMA.md` para la estructura de cada archivo.

**¿La app funciona sin internet?**
Sí, si ya tienes los archivos descargados y corres el servidor local. El servidor solo sirve los archivos estáticos.

---

## 📚 Documentación adicional

| Documento | Descripción |
|-----------|-------------|
| [ARCHITECTURE.md](ARCHITECTURE.md) | Arquitectura interna y escalabilidad futura |
| [DATA_SCHEMA.md](DATA_SCHEMA.md) | Esquemas JSON de rutas, actividades y badges |
| [PRIVACY_ETHICS.md](PRIVACY_ETHICS.md) | Privacidad, ética y límites clínicos detallados |
| [ROADMAP.md](ROADMAP.md) | V1 actual y planes para V2 |
| [TESTING_VALIDATION.md](TESTING_VALIDATION.md) | Matriz de pruebas y criterios de aceptación |
| [USER_CASES.md](USER_CASES.md) | Casos de uso por perfil (estudiante, docente, etc.) |

---

*Wellbe Quest v1 — Mapa del Buen Vivir. Prototipo educativo estático.*
*No ofrece diagnóstico, tratamiento ni recomendaciones clínicas personalizadas.*
