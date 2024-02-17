# FFMPEG - Convertir Mov a Mp4

[[PublicBrain/Index]]

Para convertir un archivo de video MOV a formato MP4 utilizando FFmpeg en la línea de comandos:

```sh
ffmpeg -i archivo_origen.mov -c:v libx264 -c:a aac -strict experimental archivo_destino.mp4
```

Reemplaza "archivo_origen.mov" con el nombre del archivo MOV que deseas convertir y "archivo_destino.mp4" con el nombre que deseas darle al archivo MP4 de salida.

Este comando utiliza los mismos parámetros que mencioné en la respuesta anterior: "libx264" como códec de video y "aac" como códec de audio. El parámetro "-strict experimental" habilita características experimentales del códec AAC.

Asegúrate de tener FFmpeg instalado en tu sistema antes de ejecutar este comando. Puedes descargar FFmpeg desde su sitio web oficial si aún no lo tienes instalado.