# CONTRIBUTING.md — Wellbe Study IA

**Versión:** 1.0 · **Última actualización:** 2026-05-05

---

## Cómo contribuir un caso nuevo

### Plantilla de caso

```json
{
  "id": "case-n{N}-{NN}",
  "level": "N1|N2|N3|N4",
  "order": 13,
  "title": "Título breve (máx 50 chars)",
  "type": "prompt_builder|claim_audit|case_simulation|evidence_matrix|policy_design|ethics_review",
  "domain": "meta-wellbe|nutricion-comunicacion|justicia-alimentaria|salud-publica|ia-responsable|institucional",
  "points": 150|200|300|400,
  "estimated_minutes": 10-25,
  "story": "Contexto narrativo: quién, dónde, qué problema (máx 200 chars)",
  "objective": "Qué debe demostrar el usuario",
  "wellbe_hint": "Mensaje del mentor Wellbe para este caso",
  "scaffolding": {
    "level": "alta|media|baja|ninguna",
    "given_prompt": "Prompt completo (solo N1)",
    "fill_in_blank": "Prompt con _______ (solo N2)",
    "hints": ["Pista 1", "Pista 2"]
  },
  "model_answer": {
    "ideal_prompt": "El prompt que un experto construiría",
    "prompt_analysis": "Por qué funciona este prompt",
    "source": "Fuentes citadas"
  },
  "wellbe_principle": "principio_ético",
  "safety_note": "Nota de seguridad con derivación a RDN"
}
```

### Checklist de revisión

```
CONTENIDO
[ ] La historia describe un escenario realista y contextualizado
[ ] El objetivo es medible y observable
[ ] El scaffolding corresponde al nivel (alta=N1, media=N2, baja=N3, ninguna=N4)
[ ] El prompt modelo activa el modo correcto de Wellbe
[ ] El análisis del prompt explica POR QUÉ funciona

ÉTICA
[ ] Ninguna respuesta correcta implica diagnóstico o prescripción
[ ] La safety note menciona derivación a RDN cuando aplica
[ ] El lenguaje no estigmatiza alimentos ni comunidades
[ ] Si hay claims, las explicaciones incluyen fuente de nivel 1

TÉCNICO
[ ] id es único en cases.json
[ ] type es un tipo registrado
[ ] domain existe en config.json
[ ] points corresponde al nivel: N1=150, N2=200, N3=300, N4=400
[ ] Si type=prompt_builder → quiz incluido
[ ] Si type=claim_audit → claims[] incluido
[ ] Si type=ethics_review → ethics_scenarios[] incluido
```

### Proceso

1. Fork del repositorio
2. Crear rama: `content/nombre-del-caso`
3. Añadir el caso al final de `data/cases.json`
4. PR con checklist completado
5. Revisión (nutricional + ética + técnica)
6. Merge y entrada en CHANGELOG.md

---

*Toda contribución pasa por revisión humana. Wellbe Study IA es educación, no prescripción.*
