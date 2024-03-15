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
# FFMPEG - Convertir Mp4 a Mp3 (Extraer audio)

[[PublicBrain/Index]]

Para convertir un archivo MP4 a un archivo MP3 e incrustar la imagen del MP4 como carátula en el archivo MP3 resultante. Aquí tienes el comando que puedes utilizar:

```sh
ffmpeg -i input.mp4 -i input.mp4 -map 0:a -map 1:v -c:a libmp3lame -b:a 192k -id3v2_version 3 -metadata:s:v title="Album cover" -metadata:s:v comment="Cover (Front)" output.mp3
```

Explicación de los parámetros:

- `-i input.mp4`: Especifica el archivo de entrada MP4.
- `-i input.mp4`: Especifica nuevamente el archivo de entrada MP4. Esto asegurará que la imagen se tome de este archivo.
- `-map 0:a`: Mapea la pista de audio del primer archivo de entrada.
- `-map 1:v`: Mapea el flujo de video del segundo archivo de entrada (la imagen).
- `-c:a libmp3lame`: Codifica el audio en formato MP3 usando el codificador libmp3lame.
- `-b:a 192k`: Establece la tasa de bits de audio en 192 kbps. Puedes ajustar esto según tus preferencias.
- `-id3v2_version 3`: Especifica la versión 3 de ID3 tags para la información del archivo MP3.
- `-metadata:s:v title="Album cover"`: Agrega el título de la carátula al archivo MP3.
- `-metadata:s:v comment="Cover (Front)"`: Agrega un comentario que indica que es la carátula frontal.
- `output.mp3`: Especifica el nombre del archivo de salida MP3.

Asegúrate de reemplazar `input.mp4` con el nombre de tu archivo MP4 de entrada y `output.mp3` con el nombre deseado para el archivo MP3 de salida. Este comando tomará el flujo de audio del archivo MP4 y lo convertirá a MP3, al mismo tiempo que incrustará la imagen del MP4 como carátula en el archivo MP3 resultante.