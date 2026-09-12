# Reglas para quien trabaje en este repositorio (Claude, Hermes, Eagle o una persona)

Este repositorio es **PÚBLICO**. Todo lo que entra aquí lo puede ver cualquiera.

## Lo que nunca entra
- Claves, tokens, contraseñas, ids de credenciales, direcciones IP de servidores,
  archivos `.env`, la carpeta `.secretos/`.
- Correos, nombres completos o datos de alumnas y clientes; capturas con datos.
- Configuración personal de Olga (arnés de Claude, ajustes, memoria).
- Material que aún no esté en la carpeta «Publicado» del Drive de OlgaDev.

## Cómo se trabaja
1. Nunca se escribe en `main`: se crea una rama (`clase/m2c5-entorno`, `docs/…`,
   `fix/…`), se hace commit en español y se abre una *pull request*. Olga aprueba.
2. Cada clase vive en `modulo-N-…/clase-NN-…/` con su `README.md` (objetivo,
   actividad, qué hay aquí, cómo abrir la app), su `app/index.html` si tiene app
   y su material (`.xlsx`, `.html`, `.pdf`).
3. Las claves de clase (`m1c1` … `m5c21`) son las mismas que usan la app y n8n:
   no se inventan otras.
4. Antes de cada commit, un escaneo de secretos: `grep -rIE "sk_|whsec_|xkeysib|api[-_]?key|password|@gmail\.com|[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}" .`
   debe salir vacío (salvo falsos positivos evidentes que se anotan).
5. Todo en español, con el tono de Olga: cercano, claro, sin humo.
6. Las apps son HTML autocontenido (sin CDN, sin claves); la lógica sensible vive
   en n8n, fuera de aquí.

## Qué más puede entrar aquí
Además de las apps y el material de cada clase, este repositorio irá recogiendo
otros elementos que cumplan el propósito de las clases y el objetivo del buen y
correcto uso de la Inteligencia Artificial: procesos de automatización (flujos de
n8n exportados y limpios de credenciales), plantillas de prompts, configuraciones
de asistentes y otras herramientas que permitan reproducir lo que se enseña.
La regla es la misma para todo: se publica lo que ya está probado y no lleva nada
privado; un flujo de n8n se exporta sin credenciales ni URLs internas, y se
documenta qué hace y qué hay que rellenar para usarlo.

## Licencias
- Código de las apps: MIT (`LICENSE-codigo.md`).
- Plantillas y material: CC BY-NC 4.0 (`LICENSE-material.md`).
