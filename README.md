# SSOP · Capturador de campo

Interfaz de captura de productividad mensual de los promotores de Promoción de
la Salud, JS XIX Texcoco (ISEM). Publicado con GitHub Pages.

## Por qué existe este repositorio

El capturador vivía servido por el propio Apps Script (`/exec`). En los
teléfonos de campo eso falla: Chrome en Android va firmado con una cuenta de
Google, y Google enruta `script.google.com` por índice de cuenta, con lo que el
despliegue se resuelve contra la equivocada y sale "No se pudo abrir el
archivo". En incógnito abría, pero el incógnito borra `localStorage` al cerrar
y con él la configuración del promotor, el borrador y la cola offline.

Sirviendo el HTML desde aquí, el promotor nunca carga una página de
`script.google.com`. El enrutamiento por cuenta desaparece y `localStorage`
persiste con normalidad.

## Cómo habla con el backend

`index.html` manda POST a la URL `/exec` de la implementación de Apps Script
(constante `ENDPOINT_DEFAULT`). El `Content-Type` es `text/plain` a propósito:
con `application/json` el navegador exige una verificación previa (OPTIONS) que
Apps Script no responde, porque no existe `doOptions`.

## Este archivo es generado, no se edita aquí

La fuente está en el repositorio privado `ssop-evaluacion-promotores`, en
`ssop/capturador/capturador.html`. Para actualizar, se regenera desde allí con
`ssop/publicar_capturador.sh` — así el endpoint queda incrustado y las dos
copias no se separan.
