---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:30:55.000Z
modified: 2024-04-03T20:19:14.673Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 23
nav_primary: []
nav_secondary: []
tags: []
---
# FFMPEG - Convertir Wmv a Mp4

[[PublicBrain/Index]]

Para convertir un archivo de video WMV a formato MP4 utilizando FFmpeg en la línea de comandos, puedes seguir estos pasos:

1. Abre una terminal o línea de comandos en tu sistema.
2. Navega al directorio donde se encuentra el archivo WMV o proporciona la ruta completa al archivo.
3. Ejecuta el siguiente comando para realizar la conversión:

bashCopy code

`ffmpeg -i archivo_origen.wmv -c:v libx264 -c:a aac -strict experimental archivo_destino.mp4`

Reemplaza "archivo_origen.wmv" con el nombre del archivo WMV que deseas convertir y "archivo_destino.mp4" con el nombre que deseas darle al archivo MP4 de salida.

En este comando, estamos utilizando los códecs de video "libx264" y de audio "aac" para la conversión. El parámetro "-strict experimental" se utiliza para habilitar características experimentales del códec AAC.

Una vez que el proceso haya terminado, tendrás un archivo MP4 resultante en el mismo directorio o la ubicación especificada.

Asegúrate de tener FFmpeg instalado en tu sistema antes de ejecutar este comando. Puedes descargar FFmpeg desde su sitio web oficial si aún no lo tienes instalado.