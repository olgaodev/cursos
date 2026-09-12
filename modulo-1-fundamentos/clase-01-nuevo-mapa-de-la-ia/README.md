# Clase 1 · El nuevo mapa de la IA

**Módulo 1 · Fundamentos**

## Objetivo

Entender qué ha cambiado de verdad con la IA generativa — no la promesa,
el mapa real de lo que hoy puedes delegar — y salir con la primera pieza
de trabajo: tus propias tareas manuales, puestas en negro sobre blanco.

## Actividad

Enumeras **3 tareas que hoy haces a mano** y que podrías delegar. Por cada
una, la app calcula cuánto tiempo te está costando al mes y con qué tipo
de solución (checklist, automatización, asistente de IA...) tiene más
sentido resolverla. Al final puedes copiar tu diagnóstico a una hoja de
cálculo propia para seguir trabajando sobre él.

## Qué hay en esta carpeta

```
app/index.html                    ← la app de la clase (HTML autocontenido)
app/favicon.svg                   ← icono, copia del que usa olgadev.com
app/assets/fonts/                 ← la tipografía Bricolage Grotesque (misma que el sitio)
matriz-diagnostico-tareas.xlsx    ← la matriz para seguir el diagnóstico fuera de la app
```

## Cómo abrirlo

- **La app en vivo**: [olgadev.com/cursos/m1c1/demo](https://olgadev.com/cursos/m1c1/demo).
- **En local**: sirve la carpeta `app/` con cualquier servidor estático y
  entra por una ruta que termine en `/demo/` (por ejemplo
  `python3 -m http.server` desde dentro de `app/` y abrir
  `http://localhost:8000/`, o copiar la carpeta a `demo/` y servir desde
  ahí) — así la app arranca en modo demo, sin llamar a ningún servidor.
  Si simplemente haces doble clic en `app/index.html` (`file://...`), la
  app cree que llevas un token real y probará a consultar la API en vivo:
  no falla nada visualmente grave, pero verás un error de red en la
  consola porque no hay token que consultar.
- **La matriz**: abre `matriz-diagnostico-tareas.xlsx` con Excel, Google
  Sheets o cualquier hoja de cálculo compatible.

> Nota técnica: la app referencia una URL de «copiar a Google Sheets»
> todavía sin publicar (aparece como `PENDIENTE_ANGIE` en el código) — el
> resto de la app funciona igual sin ella, solo falta ese enlace de copia.

## Licencia

El código de `app/` es MIT (ver [`../../LICENSE-codigo.md`](../../LICENSE-codigo.md)).
La matriz es CC BY-NC 4.0 (ver [`../../LICENSE-material.md`](../../LICENSE-material.md)):
úsala en tu negocio, no la revendas.
