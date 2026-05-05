# Primer de Seguimiento

## Estado Actual

Wellbe Quest v1 - Mapa del Buen Vivir esta implementado como MVP estatico en la raiz del repositorio. El repo esta conectado y sincronizado con GitHub.

## Como Ejecutar

Desde la raiz del proyecto:

```bash
python3 -m http.server 8000
```

Luego abrir:

```text
http://localhost:8000
```

No abrir `index.html` directamente si se quiere probar la carga de JSON, porque el navegador puede bloquear `fetch` de archivos locales.

## Proxima Prioridad Recomendada

Hacer prueba manual completa de aceptacion:

1. Abrir la app en navegador desde servidor local.
2. Confirmar que cargan las 4 rutas, 12 actividades, 6 badges y 4 avatars.
3. Seleccionar un avatar.
4. Completar una actividad.
5. Confirmar puntos, nivel, badge de primer paso y estadisticas.
6. Completar las 3 actividades de una ruta.
7. Confirmar progreso de ruta al 100% y badge de ruta completa.
8. Completar 6 actividades y confirmar badge de mitad del mapa.
9. Completar las 12 actividades y confirmar badge de mapa completo.
10. Recargar la pagina y verificar persistencia local.
11. Exportar progreso JSON.
12. Reiniciar progreso.
13. Importar el JSON exportado.
14. Confirmar restauracion de progreso.
15. Probar navegacion con teclado.
16. Probar vista movil.

## Correcciones Recomendadas de la Auditoria

- Agregar `aria-pressed` a botones de avatar seleccionado y actividades completadas.
- Anunciar cambios de puntos/badges en una region viva.
- Agregar confirmacion antes de reiniciar progreso.
- Agregar confirmacion antes de sobrescribir progreso importado.
- Mejorar Wellbe con mensajes locales contextuales por ruta o actividad.
- Actualizar el `README.md` raiz para que describa el MVP actual.

## Mantener Fuera de Alcance por Ahora

- Backend.
- Supabase.
- OAuth.
- API externa.
- IA externa.
- Telemetria remota.
- Analitica.
- Perfiles remotos.
- Datos personales.
- Recomendaciones clinicas o dietas personalizadas.

## Comandos Utiles

Validar JSON:

```bash
jq empty data/*.json
```

Buscar servicios externos activos:

```bash
rg "https?://|supabase|oauth|analytics|telemetry|cdn|api" index.html data
```

Ver estado Git:

```bash
git status --short --branch
```

Subir cambios:

```bash
git add .
git commit -m "Describe change"
git push
```

