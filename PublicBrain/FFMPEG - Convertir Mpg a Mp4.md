---
iaStatus: 0
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:30:55.000Z
modified: 2024-03-14T21:53:36.153Z
ver_major: 0
ver_minor: 1
ver_rev: 22
nav_primary: []
nav_secondary: []
tags: []
---
# FFMPEG - Convertir Mpg a Mp4

[[PublicBrain/Index]]

Para convertir un archivo de video MPG a formato MP4 utilizando la herramienta FFmpeg en la línea de comandos, puedes seguir estos pasos:

1. Abre una terminal o línea de comandos en tu sistema.
2. Navega al directorio donde se encuentra el archivo MPG o proporciona la ruta completa al archivo.
3. Ejecuta el siguiente comando para realizar la conversión:

```sh
ffmpeg -i archivo_origen.mpg -c:v libx264 -c:a aac -strict experimental archivo_destino.mp4
```

Reemplaza "archivo_origen.mpg" con el nombre del archivo MPG que deseas convertir y "archivo_destino.mp4" con el nombre que deseas darle al archivo MP4 de salida.

En este comando, estamos utilizando los códecs de video "libx264" y de audio "aac" para la conversión. El parámetro "-strict experimental" se utiliza para habilitar características experimentales del códec AAC.

Después de ejecutar el comando, FFmpeg comenzará a procesar el archivo y realizará la conversión. Una vez que el proceso haya terminado, tendrás un archivo MP4 resultante en el mismo directorio o la ubicación especificada.

Recuerda que debes tener FFmpeg instalado en tu sistema para poder ejecutar este comando. Si no lo tienes instalado, puedes descargarlo desde el sitio web oficial de FFmpeg.