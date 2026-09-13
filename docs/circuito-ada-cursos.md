# Cómo entrega Ada el material de una clase (circuito en producción desde el 13-sep-2026)

Este documento es para cualquier agente (Eagle, Hermes, Claude) o persona que trabaje en
este repositorio. Describe **qué hace Ada y qué pasa después**, sin secretos ni datos de
nadie. Si cambias algo del circuito, actualiza este archivo en la misma PR.

## El guion de Ada (fuente de verdad: Olga, dictado el 12-sep-2026)

1. Alguien ve un vídeo o una publicación y escribe a Ada en olgadev.com.
2. Ada identifica la clase. Si no está claro, pide **una sola vez** el enlace del vídeo.
3. Ada pide **solo nombre y correo**, y explica que es para enviar el material (enlace a la
   actividad en línea + PDF). Nunca oficio, sector, teléfono, franja horaria ni citas.
4. Ada pregunta si prefiere **hacer la actividad en línea o descargar el archivo**.
5. Ada ofrece, **aparte y como opcional**, recibir información sobre los cursos o un aviso
   cuando se publique uno nuevo. Si dice sí, confirma que aprueba usar nombre y correo
   solo para eso. Si dice no, le dice que su información será solo para enviarle el
   material, y que el material lo recibe igual.
6. Ada confirma que lo envía ahora y que revise la carpeta de spam. Sin plazos, sin
   «horario laboral»: Ada atiende a cualquier hora, los 7 días.

## Lo que pasa por detrás (n8n, cuenta de Olga)

- Ada no ejecuta acciones: al tener los cuatro datos escribe una línea de sistema que el
  chat no muestra. n8n la lee y llama al **registro**.
- **Registro**: valida la clase (21 claves `m1c1`…`m5c21`), guarda los dos consentimientos
  (material y, si lo hubo, promoción) con fecha y texto, genera un enlace personal con
  token (caduca a los 90 días) y avisa a la Torre de Control de Olga como lead de curso.
- **Correo**: se envía desde `cursos@olgadev.com` (Brevo) con el enlace a la actividad y el
  PDF; un segundo correo lleva el resultado cuando la persona termina la actividad. Los
  rebotes y bajas vuelven por webhook y se respetan.
- **App de la clase**: `olgadev.com/cursos/<clase>/<token>` (demo pública en `/demo`).
  Guarda el progreso por token y, al terminar, dispara el correo del resultado. La matriz
  se entrega como Google Sheets con la instrucción «Archivo → Hacer una copia».
- Si el registro falla, la persona recibe «No he podido guardar tu registro, ¿me repites
  tu nombre y tu correo?» y la Torre recibe un aviso. Nunca se le dice que se guardó si
  no fue así.

## Lo que un agente debe saber antes de tocar nada

- El texto del guion vive en el flujo web de n8n (preámbulo del nodo «Preparar»), no en el
  agente Ada de OpenClaw. Cambiar el guion = cambiar ese preámbulo, con respaldo previo.
- Los modelos gratuitos se saturan: Ada lleva un modelo principal y tres de respaldo. Si
  el chat responde «escríbeme por WhatsApp», es el modelo, no el circuito.
- Datos personales de las personas inscritas: **nunca** en este repositorio ni en
  ejecuciones de prueba con correos ajenos. Las pruebas se hacen con correos propios y se
  borran después.
- Detalle técnico (ids, scripts, respaldos) en el repositorio privado de Olga
  (`eagle_hermes/docs/cursos/`), al que tienen acceso Claude, Eagle y Hermes.
