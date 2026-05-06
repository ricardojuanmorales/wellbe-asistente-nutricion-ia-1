# CONTINUIDAD_SESION.md — Wellbe Study IA

**Fecha de cierre:** 2026-05-06  
**Repositorio:** `git@github.com:ricardojuanmorales/wellbe-asistente-nutricion-ia-1.git`  
**Rama:** `main`  
**Estado:** MVP estático completado, corregido y sincronizado

---

## 1. Compendio de situación

Wellbe Study IA es una SPA educativa gamificada construida con HTML, CSS y JavaScript vanilla. La app permite resolver 12 casos de estudio sobre nutrición, comunicación en salud, justicia alimentaria e IA responsable, con Wellbe IA como mentor pedagógico.

La versión actual usa datos externos en JSON cargados con `fetch()` desde:

- `data/config.json`
- `data/cases.json`
- `data/badges.json`

El progreso del usuario se guarda en `localStorage`. No hay backend, cuentas, cookies, analíticas ni envío de datos a servidores externos en esta versión.

### Estado técnico actual

| Área | Estado |
|------|--------|
| SPA principal | `index.html` funcional |
| Datos educativos | JSON externos en `/data/` |
| Niveles | N1, N2, N3, N4 |
| Casos | 12 casos, 3 por nivel |
| Badges | 6 badges vinculados a principios éticos |
| Persistencia | `localStorage` |
| Export/import | JSON local |
| Despliegue | Preparado para GitHub Pages |
| Repo local/remoto | Sincronizado con `origin/main` |

### Incidente resuelto

Se detectó un error de carga en navegador: los archivos `badges.json`, `cases.json` y `config.json` devolvían `404` porque `index.html` los buscaba bajo `data/`, pero estaban en la raíz del repositorio.

Resolución aplicada:

- Se creó la carpeta `data/`.
- Se movieron los tres JSON a la ruta esperada por `index.html`.
- Se validó que los tres JSON fueran parseables.
- Se verificó que las rutas HTTP locales respondieran `200 OK`.
- Se publicó el arreglo en GitHub.

Commits clave:

| Commit | Descripción |
|--------|-------------|
| `eccf52e` | `Fix JSON data paths` |
| `7bdf6e8` | `Update session closure docs` |

### Documentación vigente

- `README.md`: descripción pública del proyecto.
- `README_Project.md`: guía rápida de uso y estructura.
- `ARCHITECTURE.md`: arquitectura y decisiones técnicas.
- `DATA_SCHEMA.md`: estructura de `config.json`, `cases.json` y `badges.json`.
- `WELLBE_INTEGRATION.md`: rol pedagógico de Wellbe.
- `PRIVACY_ETHICS.md`: privacidad, límites y marco ético.
- `ROADMAP.md`: fases, estado de cierre y próximos pasos.
- `CHANGELOG.md`: historial de versión y sincronización.
- Guías N1-N4, docente, prompts y semáforo de riesgo.

---

## 2. Primer de continuidad

Este proyecto debe continuarse como una herramienta educativa de bajo riesgo, privada por defecto y fácil de desplegar. La prioridad inmediata no es añadir complejidad técnica, sino validar la experiencia con usuarios reales y confirmar que el despliegue público carga correctamente los JSON.

### Próximo punto de partida

1. Abrir GitHub Pages y confirmar que no hay errores `404` en consola.
2. Completar un recorrido mínimo:
   - cargar la app;
   - crear perfil local;
   - abrir caso N1-01;
   - responder quiz;
   - completar caso;
   - confirmar puntos y badge;
   - exportar progreso JSON.
3. Documentar cualquier fricción observada durante esa prueba.

### Prioridades recomendadas

| Prioridad | Acción |
|-----------|--------|
| Alta | Verificar GitHub Pages en navegador real |
| Alta | Hacer piloto con 5-10 usuarios |
| Media | Corregir README público si todavía muestra placeholder de clonación |
| Media | Añadir protocolo breve de prueba docente |
| Media | Registrar feedback del piloto en `ROADMAP.md` |
| Baja | Evaluar migración futura a React/Vite |

### Restricciones que conviene preservar

- Mantener privacidad local por defecto.
- No introducir backend en V1.
- No solicitar datos personales de salud.
- No convertir Wellbe en sustituto clínico.
- Conservar los JSON externos como fuente editable por docentes.
- Mantener el diseño y lenguaje consistentes con el ecosistema Wellbe.

### Riesgos pendientes

- GitHub Pages puede tardar en reflejar cambios después del push.
- Si se abre `index.html` con `file://`, los JSON pueden fallar por CORS.
- El README principal aún debe revisarse contra el nombre real del repositorio si se usa como documentación pública primaria.
- No hay pruebas automatizadas; la validación actual es manual y por HTTP local.

---

## 3. Prompt de activación

Usa este prompt para retomar el proyecto en una nueva sesión de Codex:

```md
Estoy trabajando en el repositorio `wellbe-asistente-nutricion-ia-1`, una SPA educativa llamada Wellbe Study IA.

Contexto:
- Rama principal: `main`.
- Remoto: `git@github.com:ricardojuanmorales/wellbe-asistente-nutricion-ia-1.git`.
- Stack: HTML, CSS y JavaScript vanilla en `index.html`.
- Datos externos: `data/config.json`, `data/cases.json`, `data/badges.json`.
- Persistencia: `localStorage`.
- No hay backend ni dependencias de build.
- GitHub Pages debe servir la app como sitio estático.

Estado reciente:
- Se corrigió un error de `404` porque los JSON estaban en la raíz y `index.html` los buscaba en `data/`.
- Commit del fix: `eccf52e Fix JSON data paths`.
- Commit de cierre documental: `7bdf6e8 Update session closure docs`.
- El repo quedó sincronizado con `origin/main`.

Antes de editar:
1. Ejecuta `git status -sb`.
2. Revisa `ROADMAP.md`, `CHANGELOG.md` y `CONTINUIDAD_SESION.md`.
3. No reviertas cambios del usuario.

Objetivo sugerido para continuar:
Verificar GitHub Pages en navegador real, confirmar que `data/*.json` carga sin `404`, hacer una prueba manual del caso N1-01 y documentar cualquier hallazgo.

Si vas a modificar el repo:
- Mantén los cambios acotados.
- Actualiza documentación si cambia el estado del proyecto.
- Valida JSON con `jq empty data/*.json` cuando edites datos.
- Commit y push a `origin/main` solo cuando el estado esté limpio y revisado.
```

---

## Checklist de cierre

- [x] JSON ubicados en `/data/`.
- [x] Fix publicado en GitHub.
- [x] Documentos de cierre actualizados.
- [x] Compendio de continuidad creado.
- [ ] Verificación final en GitHub Pages desde navegador.
- [ ] Piloto con usuarios.
