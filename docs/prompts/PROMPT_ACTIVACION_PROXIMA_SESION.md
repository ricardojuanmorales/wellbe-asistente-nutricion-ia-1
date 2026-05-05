# Prompt de Activacion para Proxima Sesion

Actua como agente de desarrollo dentro del workspace de VS Code del repositorio:

```text
/Users/ricardomoralesdejesus/wellbe-quest-mvp-1
```

Proyecto:

```text
Wellbe Quest v1 - Mapa del Buen Vivir
```

Repositorio GitHub:

```text
https://github.com/ricardojuanmorales/wellbe-quest-mvp-1
```

## Contexto

El MVP V1 ya esta implementado como aplicacion estatica en la raiz del repo. Usa:

- `index.html` como monolito HTML/CSS/JS;
- JSON editable en `data/`;
- documentacion Markdown en `docs/`;
- progreso local con `localStorage` bajo la clave `wellbeQuestV1Progress`;
- exportacion/importacion JSON;
- sin backend, Supabase, OAuth, APIs externas, telemetria remota, frameworks pesados ni dependencias instaladas.

## Antes de Cambiar Codigo

1. Revisa `git status --short --branch`.
2. Lee:
   - `AGENTS.md`;
   - `docs/session/COMPENDIO_SESION.md`;
   - `docs/followup/PRIMER_SEGUIMIENTO.md`;
   - `docs/TESTING_VALIDATION.md`.
3. No agregues backend ni servicios externos.
4. No cambies el esquema JSON sin actualizar `docs/DATA_SCHEMA.md`.
5. No introduzcas datos personales reales.

## Primera Tarea Recomendada

Ejecuta una prueba manual completa de aceptacion del MVP:

- carga local desde servidor estatico;
- seleccion de avatar;
- completar actividades;
- verificar puntos, niveles, badges y estadisticas;
- recargar para comprobar persistencia;
- exportar progreso;
- reiniciar;
- importar progreso;
- verificar restauracion;
- probar navegacion por teclado y vista movil.

## Si Se Aprueban Mejoras

Prioriza estas correcciones pequenas:

1. `aria-pressed` para estados seleccionados/completados.
2. Region viva para anunciar cambios de progreso.
3. Confirmacion antes de reiniciar progreso.
4. Confirmacion antes de sobrescribir progreso importado.
5. Mensajes locales de Wellbe por ruta o actividad.
6. Actualizacion del `README.md` raiz.

## Criterio de Cierre

La sesion debe terminar con:

- cambios validados;
- documentacion actualizada si aplica;
- commit claro;
- push a `main`;
- resumen breve de lo realizado y pruebas ejecutadas.

