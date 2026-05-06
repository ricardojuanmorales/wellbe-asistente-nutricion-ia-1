# Guía de Prompts para Wellbe IA

**Para:** Todos los niveles · **Referencia permanente**

---

## Anatomía de un buen prompt

Un prompt efectivo para Wellbe tiene **cinco partes**:

```
1. NIVEL      → básico, intermedio, avanzado
2. MODO       → Claro, Docente, Investigador, Auditor, Evaluador
3. TEMA       → específico y delimitado
4. CONTEXTO   → público, territorio, cultura, situación
5. LÍMITE     → sin prescripción, fuente requerida, incertidumbre
```

---

## Plantillas por nivel

### N1 — Modo Claro

```
Wellbe, explícame [TEMA] en nivel básico,
con un ejemplo cotidiano usando [CONTEXTO CULTURAL],
y sin entrar en recomendaciones clínicas.
```

**Cuándo usarlo:** Preguntas educativas generales. Equivale a preguntarle a un docente.

**Ejemplo real:**
> "Wellbe, explícame qué son los aminoácidos esenciales en nivel básico, con un ejemplo usando arroz con habichuelas, y sin entrar en recomendaciones clínicas."

---

### N2 — Modo Operativo

```
Wellbe, crea un [FORMATO] sobre [TEMA] para [PÚBLICO].
Usa lenguaje [TONO], considera el contexto de [TERRITORIO/CULTURA]
e incluye [FUENTE + NOTA DE LÍMITES].
```

**Cuándo usarlo:** Crear materiales educativos, posts, actividades, fichas.

**Ejemplo real:**
> "Wellbe, crea un carrusel de 5 slides para Instagram sobre las 4 dimensiones de la seguridad alimentaria para audiencia general en Puerto Rico. Usa lenguaje claro y no técnico, considera que PR importa ~85% de sus alimentos e incluye al menos una fuente verificable (FAO, USDA ERS) y una nota de que es contenido educativo."

---

### N3 — Modo Investigador

```
Wellbe, activa Modo Investigador N3.
[VERBO: construye/analiza/compara/evalúa] [TEMA] en [CONTEXTO].
Formato: [TIPO DE SALIDA].
Incluye: [FUENTES DE NIVEL 1].
Contextualiza para [TERRITORIO].
Declara: qué sabe la evidencia, qué sugiere y qué no puede responder.
```

**Cuándo usarlo:** Investigación, matrices de evidencia, análisis de fuentes.

**Ejemplo real:**
> "Wellbe, activa Modo Investigador N3. Construye una matriz de evidencia sobre programas Food is Medicine con enfoque en medically tailored meals. Formato: tabla con columnas Referencia, Diseño, Muestra, Hallazgo, Limitaciones. Incluye fuentes de JAMA, NEJM, Cochrane, USDA ERS. Contextualiza para Puerto Rico: alta prevalencia diabetes tipo 2, ~85% importación. Declara qué establece la evidencia, qué sugiere pero no demuestra, y qué no puede responder."

---

### N4 — Modo Evaluador

```
Wellbe, activa Modo Evaluador N4.
Diseña [TIPO DE IMPLEMENTACIÓN] en [CONTEXTO INSTITUCIONAL].
Incluye: [ROLES + ESTRUCTURA + EVALUACIÓN + RIESGOS + MEJORA].
```

**Cuándo usarlo:** Diseño de programas, gobernanza, implementación institucional.

**Ejemplo real:**
> "Wellbe, activa Modo Evaluador N4. Diseña un piloto de 8 semanas para implementar Wellbe IA en un curso de nutrición comunitaria en el RCM-UPR. Incluye: roles humanos, estructura de cartapacios (GitHub + Obsidian), AGENTS.md, skills operativos, workflows semanales, evaluación (IEPA-Wellbe, rúbricas, portafolio), criterios de éxito medibles, riesgos éticos, plan de mitigación y ciclo de mejora continua."

---

## Modos de Wellbe disponibles

| Modo | Activación | Para qué |
|------|-----------|---------|
| Claro | Implícito en N1 | Explicaciones educativas básicas |
| Docente | "Modo Docente" | Diseño educativo, materiales |
| Social Media | "Modo Social" | Contenido para redes con revisión |
| Investigador | "Modo Investigador N3" | Matrices, fuentes, evidencia |
| Auditor Ético | "Modo Auditor Ético" | Verificación de claims |
| Datos | "Modo Datos" | Análisis de composición de alimentos |
| Evaluador | "Modo Evaluador N4" | Diseño institucional, gobernanza |
| Microbioma Prudente | "Modo Microbioma" | Temas de evidencia emergente |
| Comunitario | "Modo Comunitario" | Contextos de base comunitaria |

---

## Errores comunes en prompts

| ❌ Malo | ✅ Mejor | Por qué |
|---------|---------|---------|
| "¿Es saludable el arroz?" | "Wellbe, explícame el perfil nutricional del arroz blanco en el contexto de la dieta puertorriqueña, sin calificarlo como bueno o malo." | Sin estigmatizar; contextualizado |
| "Dame una dieta para diabéticos" | No usar Wellbe para esto. Derivar a RDN. | Límite absoluto de Wellbe |
| "Dime todo sobre nutrición" | "Wellbe, explícame los macronutrientes en nivel básico con un ejemplo caribeño." | Específico, delimitado |
| "Wellbe, haz un post viral" | "Wellbe, crea un post educativo sobre etiquetas nutricionales para audiencia joven en PR. Incluye fuente FDA y nota de límites." | Con estructura, fuente y límite |

---

## Señales de que tu prompt es bueno

- ✅ Especifica el nivel o modo de Wellbe
- ✅ Delimita el tema (no es "todo sobre X")
- ✅ Incluye contexto cultural o territorial
- ✅ Pide fuente verificable
- ✅ Establece límite ético
- ✅ No pide diagnóstico, prescripción ni plan terapéutico

---

## Señales de que tu prompt necesita mejora

- ⚠️ Es demasiado amplio ("háblame de nutrición")
- ⚠️ No especifica audiencia ni contexto
- ⚠️ No pide fuente
- ⚠️ Podría interpretarse como solicitud clínica
- ⚠️ No incluye límites éticos

---

*Wellbe · Nutrición con evidencia, cultura y cuidado.*
