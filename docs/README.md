# Wellbe Quest v1 - Mapa del Buen Vivir

Wellbe Quest v1 es un MVP educativo gamificado sobre nutricion humana, seguridad alimentaria y nutricional, agroecologia, comunidad, inteligencia artificial, salud publica y buen vivir.

La aplicacion es estatica: usa un solo `index.html`, datos JSON editables y documentacion Markdown. No usa backend, Supabase, OAuth, APIs externas, telemetria remota ni frameworks pesados.

## Estructura

```text
AGENTS.md
index.html
data/routes.json
data/activities.json
data/badges.json
data/avatars.json
data/game_config.json
docs/
exports/.gitkeep
```

## Ejecutar localmente

`index.html` carga JSON con `fetch`, asi que conviene usar un servidor estatico desde la raiz:

```bash
python3 -m http.server 8000
```

Luego abre el navegador en el puerto 8000 de localhost.

## MVP

Incluye 4 rutas, 12 actividades, 6 badges, avatar transdisciplinario, progreso local, niveles, estadisticas basicas, exportacion/importacion JSON y aviso de privacidad.
