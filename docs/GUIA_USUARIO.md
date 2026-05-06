# Guía de Usuario — WellBe Asistente de Aprendizaje Transdisciplinario

**Versión 0.1.0**

> "El conocimiento que transforma surge cuando conectamos salud, territorio, tecnología y comunidad."

---

## Índice

1. [¿Qué es WellBe?](#1-qué-es-wellbe)
2. [Cómo empezar](#2-cómo-empezar)
3. [Tu perfil educativo](#3-tu-perfil-educativo)
4. [Elige tu avatar](#4-elige-tu-avatar)
5. [Rutas de aprendizaje](#5-rutas-de-aprendizaje)
6. [Tipos de actividad](#6-tipos-de-actividad)
7. [Puntos, niveles y badges](#7-puntos-niveles-y-badges)
8. [Exportar e importar tu progreso](#8-exportar-e-importar-tu-progreso)
9. [Privacidad y límites](#9-privacidad-y-límites)
10. [Preguntas frecuentes](#10-preguntas-frecuentes)

---

## 1. ¿Qué es WellBe?

WellBe es una **plataforma educativa lúdica y gamificada** donde puedes explorar cómo la inteligencia artificial y las tecnologías emergentes se relacionan con la salud pública, la agroecología, la nutrición y el buen vivir.

### ¿Para quién es?

- Estudiantes de salud, nutrición, ciencias ambientales, educación o tecnología
- Docentes e investigadores que quieran explorar o usar el contenido
- Personas de comunidades interesadas en alfabetización crítica sobre IA y salud

### ¿Qué puedes hacer?

| | |
|---|---|
| 🗺️ | Explorar 4 rutas de aprendizaje |
| 🧩 | Completar 12 actividades interactivas de 8 tipos diferentes |
| 🏅 | Ganar badges y subir de nivel |
| 💾 | Guardar tu progreso en el navegador |
| 📤 | Exportar tu progreso como archivo JSON |
| 📥 | Importar tu progreso en otro dispositivo |

> **Importante:** WellBe es exclusivamente educativo. No ofrece diagnósticos médicos, recomendaciones nutricionales personalizadas ni tratamientos de ningún tipo. Consulta siempre a profesionales de salud calificados.

---

## 2. Cómo empezar

### Opción A — Abrir directamente en el navegador

Si descargaste el repositorio, simplemente abre `index.html` en tu navegador.

> Si las actividades no cargan, usa la Opción B.

### Opción B — Servidor local (recomendado si hay problemas)

Abre una terminal en la carpeta del proyecto y ejecuta:

```bash
# Con Python 3 (más común)
python3 -m http.server 8000
```

Luego abre en tu navegador: `http://localhost:8000`

### Opción C — GitHub Pages

Si el proyecto está publicado en GitHub Pages, accede directamente desde el enlace del repositorio.

---

## 3. Tu perfil educativo

Al entrar por primera vez, verás el formulario de perfil en la parte superior de la página.

### Campos del perfil

| Campo | Descripción | Obligatorio |
|---|---|---|
| Nombre o alias | Cómo quieres que te llame la app | No |
| Rol | Estudiante, docente, investigador/a, comunidad u otro | No |
| Consentimiento de investigación | Participación futura opcional | No — desactivado por defecto |

### Pasos

1. Escribe tu nombre o deja el campo vacío para usar "Explorador/a"
2. Selecciona tu rol si quieres
3. Haz clic en **Crear perfil**

Para editar tu perfil más adelante, ve a la sección **Perfil** y haz clic en **Editar perfil**.

> El perfil se guarda en tu navegador. No se envía a ningún servidor.

---

## 4. Elige tu avatar

En la sección **Avatar** encontrarás 4 compañías de aprendizaje. Cada una representa una forma de conectar saberes — no una apariencia física.

| Avatar | Rol | Rasgos |
|---|---|---|
| **Índigo** | Pensador/a sistémico/a | Curioso/a, analítico/a, ético/a, transdisciplinario/a |
| **Raíz** | Guardián/a de la tierra | Paciente, territorial, comunitario/a, observador/a |
| **Dato** | Analista crítico/a | Escéptico/a, riguroso/a, justo/a, claro/a |
| **Nexo** | Puente comunidad-tecnología | Empático/a, creativo/a, mediador/a, colaborativo/a |

**Para seleccionar:** haz clic sobre la tarjeta del avatar que quieras. Quedará resaltada.

---

## 5. Rutas de aprendizaje

La sección **Rutas** muestra las 4 rutas disponibles. Cada tarjeta de ruta incluye:

- **Narrativa** — el contexto y la historia de esa ruta
- **Objetivo de aprendizaje** — qué vas a explorar
- **Barra de progreso** — se llena al completar actividades de esa ruta
- **Tiempo estimado** y nivel de dificultad

### Las 4 rutas

| Ruta | Temas | Nivel |
|---|---|---|
| **IA Responsable** | Qué es la IA, sesgos, transparencia, ética en salud | Inicial |
| **Nutrición y Datos** | Evidencia nutricional, mitos, pensamiento crítico | Inicial |
| **Salud Pública Digital** | Telemedicina, brechas digitales, respuesta a brotes | Intermedio |
| **Agroecología y Buen Vivir** | Sistemas agroecológicos, soberanía alimentaria, filosofía del buen vivir | Intermedio |

---

## 6. Tipos de actividad

La sección **Actividades** muestra las 12 actividades disponibles. Haz clic en **Comenzar actividad** para abrir la ventana interactiva.

---

### Quiz — Preguntas conceptuales

**¿Cuándo aparece?** En actividades como "¿Qué hace realmente la IA?" o "Telemedicina: posibilidades y límites".

**Cómo funciona:**
1. Lee la pregunta en pantalla
2. Haz clic en la opción que consideras correcta
3. Se muestra inmediatamente la respuesta correcta con su **explicación**
4. Responde todas las preguntas para habilitar "Completar actividad"

> No hay penalización por responder incorrectamente. Cada error muestra la respuesta correcta con contexto.

---

### Semáforo de Claims — Detectar afirmaciones

**¿Cuándo aparece?** En actividades como "Semáforo de afirmaciones nutricionales".

**Cómo funciona:**
1. Lee la afirmación en cursiva
2. Haz clic en uno de los tres botones:
   - **Verdadera** — bien sustentada por evidencia
   - **Engañosa** — parcialmente correcta pero distorsionada
   - **Falsa** — incorrecta o sin base
3. Se revela el veredicto correcto con explicación
4. Evalúa todas las afirmaciones para completar

> Muchas afirmaciones comunes sobre nutrición son engañosas, no directamente falsas. Presta atención al matiz.

---

### Decisiones ramificadas

**¿Cuándo aparece?** En actividades como "Decisión ética: el algoritmo de triaje" o "La oferta de la agroindustria".

**Cómo funciona:**
1. Lee el **escenario** en el recuadro de contexto
2. Se te presentan varias opciones de decisión
3. Haz clic en la opción que eliges
4. Cada elección lleva a una rama diferente del caso
5. Al llegar al final, WellBe ofrece un **cierre reflexivo**

> No hay respuestas "correctas" fijas. El objetivo es explorar el contexto y las consecuencias de distintas decisiones.

---

### Mapa mental

**¿Cuándo aparece?** En actividades como "El ecosistema de la IA en salud" o "Sistemas agroecológicos".

**Cómo funciona:**
1. Observa el **nodo central** — el tema principal de la actividad
2. Haz clic en cada nodo de colores para **expandirlo**
3. Cada nodo muestra una descripción y ejemplos concretos
4. Abre al menos **3 nodos** para habilitar "Completar actividad"
5. Lee la **pregunta de reflexión** al final del mapa

> Intenta conectar lo que ves en el mapa con situaciones de tu contexto real.

---

### Simulación

**¿Cuándo aparece?** En actividades como "Simulación: respuesta a un brote".

**Cómo funciona:**
1. Lee la introducción y observa el **medidor de resiliencia** (comienza en 5/10)
2. En cada paso, lee el contexto y elige una decisión
3. Se muestra el **efecto** de tu decisión y el medidor cambia
4. Al completar todos los pasos, aparece la reflexión final

> El medidor sube o baja según tus decisiones. No hay "game over": el objetivo es reflexionar sobre las consecuencias sistémicas de cada elección.

---

### Reflexión — Preguntas abiertas

**¿Cuándo aparece?** En actividades como "Mi relación con la información de salud".

**Cómo funciona:**
1. Lee el mensaje de WellBe para prepararte
2. Escribe tu respuesta en los **cuadros de texto**
3. Escribe al menos 10 caracteres en uno de los campos para habilitar "Completar"
4. Haz clic en **Completar actividad**

> Tus reflexiones escritas no se guardan en esta versión. Solo se registra que completaste la actividad.

---

### Lectura — Texto con preguntas de comprensión

**¿Cuándo aparece?** En actividades como "Cómo leer evidencia nutricional" o "Buen vivir: una filosofía para otro mundo".

**Cómo funciona:**
1. Lee el **texto formativo** en el recuadro gris
2. Responde las **preguntas de comprensión** debajo del texto (funcionan igual que un quiz)
3. Responde todas las preguntas para habilitar "Completar actividad"

> Puedes releer el texto cuantas veces necesites antes de responder las preguntas.

---

### Reto — Desafío práctico con checklist

**¿Cuándo aparece?** En actividades como "Reto: mapea tu acceso a salud digital".

**Cómo funciona:**
1. Lee el contexto y la descripción del reto
2. Realiza cada paso del checklist en tu contexto real (puede implicar buscar información, hablar con alguien, observar tu entorno)
3. Marca cada casilla al completar el paso
4. Al marcar todos los pasos, aparece el mensaje de cierre de WellBe y puedes "Completar actividad"

> Los retos conectan el aprendizaje con la realidad de tu comunidad o entorno. No hay respuestas que verificar — la experiencia es el aprendizaje.

---

## 7. Puntos, niveles y badges

### Puntos por actividad

Cada actividad otorga entre 20 y 45 puntos al completarse. Los puntos se acumulan automáticamente.

### Niveles

| Nivel | Nombre | Puntos mínimos |
|---|---|---|
| 1 | Explorador/a | 0 pts |
| 2 | Conector/a | 80 pts |
| 3 | Analista | 180 pts |
| 4 | Co-creador/a | 300 pts |

WellBe te muestra un mensaje motivador cada vez que subes de nivel.

### Badges

Los badges se desbloquean automáticamente al cumplir su condición:

| Badge | Cómo se desbloquea |
|---|---|
| **Primer paso** | Completar 1 actividad |
| **Ruta completa** | Terminar todas las actividades de 1 ruta |
| **Mitad del camino** | Completar 6 actividades |
| **Aprendizaje completo** | Completar las 12 actividades |
| **Ético/a de IA** | Completar la ruta "IA Responsable" entera |
| **Retador/a** | Completar 1 actividad tipo Reto |

Los badges aparecen en la sección **Badges** de la página. Los ganados se muestran resaltados.

---

## 8. Exportar e importar tu progreso

Tu progreso se guarda automáticamente en el navegador mientras usas la app. Para llevarlo a otro dispositivo o guardarlo de forma segura, usa las funciones de la sección **Progreso**.

### Exportar

1. Ve a la sección **Progreso**
2. Haz clic en **Exportar progreso**
3. Se descarga un archivo `.json` con la fecha de hoy (por ejemplo: `wellbe-asistente-progreso-2026-05-05.json`)
4. Guárdalo en tu computadora, nube o USB

El archivo contiene: actividades completadas, puntos, nivel, badges y avatar seleccionado.

### Importar

1. Ve a la sección **Progreso**
2. Haz clic en **Importar JSON**
3. Selecciona el archivo `.json` exportado previamente
4. La app valida el archivo y carga tu progreso

> Importar reemplaza el progreso actual. Si quieres conservarlo, expórtalo primero.

### Reiniciar progreso

1. Haz clic en **Reiniciar**
2. Aparece una confirmación — acepta para borrar
3. El progreso vuelve a cero (el perfil y el avatar seleccionado no se borran)

---

## 9. Privacidad y límites

### Lo que WellBe guarda (solo en tu navegador)

- Actividades completadas (IDs)
- Avatar seleccionado
- Puntos, nivel y badges calculados
- Nombre/alias y rol de tu perfil (opcional)

### Lo que WellBe NO guarda ni envía

- Tus respuestas escritas en reflexiones
- Los pasos que marcaste en los retos
- Información de identificación personal
- Datos médicos o nutricionales
- Datos de ubicación
- Historial de navegación

### Lo que WellBe NO hace

- No envía datos a servidores externos
- No tiene cuentas de usuario ni contraseñas
- No usa cookies de rastreo
- No ofrece diagnósticos de salud
- No recomienda dietas ni tratamientos
- No compara usuarios entre sí

### Aviso clínico

WellBe es una herramienta educativa. **No reemplaza** la atención de profesionales de salud, nutrición, psicología ni trabajo social. Ante cualquier duda o situación de salud, consulta a un profesional calificado.

---

## 10. Preguntas frecuentes

**¿Puedo usar la app sin crear un perfil?**
Sí. El perfil es completamente opcional. Sin él, la app funciona con el nombre "Explorador/a".

**¿Qué pasa si cierro el navegador?**
Tu progreso se guarda automáticamente en el navegador. Al volver, todo estará como lo dejaste, siempre que uses el mismo navegador en el mismo dispositivo.

**¿Puedo usar la app en varios dispositivos?**
En esta versión el progreso es local a cada navegador. Usa **Exportar** para llevar tu progreso a otro dispositivo e **Importar** para cargarlo allí.

**¿Puedo reiniciar una actividad ya completada?**
Sí. Cada actividad completada muestra el botón **Reiniciar** para volver a realizarla. Los puntos se recalculan automáticamente.

**¿Mis reflexiones escritas se guardan?**
No en esta versión. Solo se registra que completaste la actividad. Las reflexiones son para ti.

**¿El consentimiento de investigación recopila mis datos?**
No. En v0.1 es un campo preparado para una función futura. Activarlo no hace nada ni envía datos.

**¿Cómo puede un docente editar el contenido?**
Los archivos `data/*.json` son editables con cualquier editor de texto. Consulta `docs/DATA_SCHEMA.md` para entender la estructura de cada archivo.

**¿La app funciona sin internet?**
Sí, si ya tienes los archivos descargados. Ejecuta el servidor local y todo funciona sin conexión.

**¿Por qué no funciona si abro el archivo directamente con doble clic?**
El navegador bloquea las solicitudes de archivos locales por seguridad. Usa `python3 -m http.server 8000` y accede desde `localhost:8000`.

---

*WellBe — Asistente de Aprendizaje Transdisciplinario · v0.1.0 · Plataforma educativa estática.*
*No ofrece diagnóstico, tratamiento ni recomendaciones clínicas personalizadas.*
