# Proyecto — SSOP — Capturador de campo (GitHub Pages)

## Propósito

Servir el capturador de productividad mensual de los promotores desde GitHub Pages, para que el promotor nunca cargue una pagina de `script.google.com`.

## Arquitectura

Un solo `index.html`. Manda POST a la URL `/exec` de la implementacion de Apps Script (constante `ENDPOINT_DEFAULT`).

## Stack

HTML estatico publicado con GitHub Pages.

## Entradas

Capturado por el promotor en el navegador; borrador y cola offline en `localStorage`.

## Salidas

POST al backend de Apps Script del proyecto `supervision-promotores`.

## Datos requeridos

> Pendiente: completar al trabajar el proyecto. No inventar.

## Integraciones

Backend Apps Script de SSOP; GitHub Pages.

## Comandos principales

No se edita aqui. Se regenera desde `ssop/publicar_capturador.sh` del proyecto origen.

## Validaciones

> Pendiente: completar al trabajar el proyecto. No inventar.

## Restricciones

- **`index.html` es generado, no se edita en este repositorio.** La fuente esta en `ssop/capturador/capturador.html` del repositorio `ssop-evaluacion-promotores`.
- El `Content-Type` del POST es `text/plain` a proposito: con `application/json` el navegador exige una verificacion previa (OPTIONS) que Apps Script no responde, porque no existe `doOptions`.

---

Registrado en el JST AI Workspace como `supervision-capturador`.
Ver `../JST-AI-WORKSPACE/projects.yaml`.
