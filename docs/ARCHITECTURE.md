# Arquitectura

## Enfoque

Wellbe Quest v1 es un monolito HTML estatico. El navegador carga `index.html`, solicita archivos JSON desde `data/` y guarda progreso en `localStorage`.

## Flujo de datos

1. `index.html` carga rutas, actividades, badges, avatars y configuracion.
2. La app normaliza progreso desde `localStorage` con la clave `wellbeQuestV1Progress`.
3. Cada actividad completada recalcula puntos, nivel, progreso por ruta, badges y estadisticas.
4. La exportacion descarga un JSON local.
5. La importacion lee un JSON elegido por la persona usuaria, valida IDs conocidos e ignora valores desconocidos.

## Restricciones

- Sin backend.
- Sin base de datos remota.
- Sin cuentas ni OAuth.
- Sin Supabase.
- Sin APIs externas.
- Sin telemetria remota.
- Sin dependencias instaladas.

## Escalabilidad

La separacion entre UI monolitica y datos JSON permite editar contenido educativo sin tocar la logica principal. Una futura V2 podria modularizar JavaScript, agregar pruebas automatizadas o introducir persistencia remota solo despues de definir privacidad, consentimiento y gobernanza.
