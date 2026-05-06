# PRIVACY_ETHICS.md — Wellbe Study IA

**Versión:** 1.0 · **Última actualización:** 2026-05-05

---

## 1. Principios éticos integrados al juego

Los 8 principios de Wellbe IA están implementados como mecánicas de juego:

| Principio | Implementación en Study IA |
|-----------|---------------------------|
| **Veracidad** | Cada caso cita fuentes; el prompt modelo incluye referencia verificable |
| **Prudencia** | Safety note obligatoria en cada caso; casos de ethics_review enseñan los límites |
| **Justicia alimentaria** | Casos sobre desiertos alimentarios, SNAP, colmados; badge dedicado |
| **Equidad cultural** | Casos contextualizados en Puerto Rico/Caribe; prompts modelo piden tono respetuoso |
| **Responsabilidad informacional** | Evaluación de calidad de prompts; fuentes de nivel 1 requeridas en N3 |
| **Confidencialidad** | No se solicitan datos de salud; almacenamiento local |
| **Comunicación no estigmatizante** | Caso N1-03 (la abuela y la yuca) enseña explícitamente este principio |
| **Supervisión humana** | Casos N4 incluyen gobernanza; badge "Guardián ético" por detectar violaciones |

---

## 2. Política de privacidad del MVP

### Datos almacenados localmente

```json
{
  "progreso": "completedIds, points, level, earnedBadges",
  "perfil": "name (alias), role, createdAt"
}
```

**Ningún dato se transmite a ningún servidor.**

### Datos que NO se solicitan

Nombre real, correo, fecha de nacimiento, género, condiciones de salud, historial médico, ubicación, datos dietéticos, identificadores de dispositivo.

### Sin rastreo

No cookies, no analytics, no pixels, no SDKs de terceros.

### Exportación y eliminación

El usuario puede exportar (JSON), importar y eliminar su progreso en cualquier momento.

---

## 3. Contenido educativo — límites absolutos

- ❌ Nunca prescripción clínica ni diagnóstico como respuesta correcta de un caso
- ❌ Nunca recomendación de suplementos específicos
- ❌ Nunca claims de salud sin fuente de nivel 1
- ❌ Nunca lenguaje que estigmatice alimentos culturales
- ✅ Siempre fuente verificable en cada caso
- ✅ Siempre safety note con derivación a RDN
- ✅ Siempre el prompt modelo declara límites éticos

---

*Documento mantenido por el equipo de Wellbe Study IA.*
