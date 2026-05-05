# AGENTS.md

Guia para agentes que trabajen en Wellbe Quest v1 - Mapa del Buen Vivir.

## Principios

- Mantener el MVP como app estatica: `index.html`, JSON en `data/` y Markdown en `docs/`.
- No agregar backend, Supabase, OAuth, APIs externas, telemetria remota ni frameworks pesados.
- No instalar dependencias salvo aprobacion explicita y justificacion fuerte.
- Mantener la experiencia principal en espanol claro, accesible y educativo.
- Documentar cualquier cambio de esquema en `docs/DATA_SCHEMA.md`.
- Actualizar docs cuando cambien comportamientos, privacidad, testing o roadmap.

## Datos

- Los JSON deben seguir siendo editables por personas no tecnicas.
- Usar IDs estables en kebab-case.
- Verificar referencias cruzadas entre rutas, actividades, badges y avatars.
- No incluir datos personales reales ni exports de usuarios en el repo.

## Producto y Etica

- Wellbe es co-piloto educativo local, no terapeuta ni profesional clinico.
- Evitar lenguaje diagnostico, prescriptivo o culpabilizante.
- Mantener privacidad local y minimizacion de datos como defaults.
