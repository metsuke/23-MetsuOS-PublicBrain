# FFMPEG - Convertir Wmv a Mp4

[[Index]]

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