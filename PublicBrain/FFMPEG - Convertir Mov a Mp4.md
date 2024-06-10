---
iaStatus: 8
iaStatus_Model: ""
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.355Z
modified: 2024-06-10T15:26:26.919Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 29
nav_primary: 
nav_secondary: 
tags:
---
# FFMPEG - Convertir Mov a Mp4

[[PublicBrain/Index]]

Para convertir un archivo de video MOV a formato MP4 utilizando FFmpeg en la línea de comandos:

```sh
ffmpeg -i archivo_origen.mov -c:v libx264 -c:a aac -strict experimental archivo_destino.mp4
```

Reemplaza "archivo_origen.mov" con el nombre del archivo MOV que deseas convertir y "archivo_destino.mp4" con el nombre que deseas darle al archivo MP4 de salida.

Este comando utiliza los mismos parámetros que mencioné en la respuesta anterior: "libx264" como códec de video y "aac" como códec de audio. El parámetro "-strict experimental" habilita características experimentales del códec AAC.

Asegúrate de tener FFmpeg instalado en tu sistema antes de ejecutar este comando. Puedes descargar FFmpeg desde su sitio web oficial si aún no lo tienes instalado.