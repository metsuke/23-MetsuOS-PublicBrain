---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:30:55.000Z
modified: 2024-04-03T20:19:14.676Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 23
nav_primary: []
nav_secondary: []
tags: []
---
# FFMPEG - Convertir DVD a Mp4

[[PublicBrain/Index]]

Para convertir un archivo .iso que contiene un DVD a un archivo MP4 utilizando FFmpeg, puedes seguir estos pasos:

1. **Instala FFmpeg:** Si aún no tienes FFmpeg instalado en tu sistema, debes hacerlo. Puedes descargar FFmpeg desde el sitio web oficial ([https://www.ffmpeg.org/download.html](https://www.ffmpeg.org/download.html)) o utilizar un gestor de paquetes si estás en Linux.
    
2. **Monta la imagen ISO:** Primero, monta la imagen ISO en tu sistema como si fuera una unidad de DVD. Puedes hacerlo utilizando una herramienta de montaje de imágenes ISO o el comando `mount` en Linux. Por ejemplo:
    
    ```sh
    sudo mount -o loop archivo.iso /ruta/de/montaje
    ```
    
    Reemplaza `archivo.iso` con la ruta de tu archivo .iso y `/ruta/de/montaje` con la ubicación donde deseas montar la imagen.
    
3. **Convierte el DVD a MP4:** Una vez que la imagen ISO está montada, puedes usar FFmpeg para convertir el contenido del DVD a MP4. Utiliza el siguiente comando como punto de partida:
    
   ```sh
   ffmpeg -i /ruta/de/montaje/video_ts/vts_01_1.vob -vf "scale=1280:720" -c:v libx264 -preset slow -crf 22 -c:a aac -strict experimental -b:a 192k -ac 2 salida.mp4
   ```
    
    - `/ruta/de/montaje` debe reemplazarse con la ubicación donde montaste la imagen ISO.
    - `vts_01_1.vob` es el archivo de video principal en la mayoría de los DVDs, pero podría variar según el contenido del DVD. Puedes verificar los archivos dentro de la carpeta `/ruta/de/montaje/video_ts` para encontrar el archivo de video principal y ajustar el comando en consecuencia.
4. **Personaliza la conversión:** Puedes personalizar la conversión según tus preferencias. El comando anterior escala el video a 1280x720, utiliza el códec de video H.264, el códec de audio AAC y establece una velocidad de bits de audio de 192 kbps. Puedes ajustar los parámetros según tus necesidades.
    
5. **Inicia la conversión:** Una vez que hayas personalizado el comando, ejecútalo para iniciar la conversión:
    
    ```sh    
    ffmpeg -i /ruta/de/montaje/video_ts/vts_01_1.vob -vf "scale=1280:720" -c:v libx264 -preset slow -crf 22 -c:a aac -strict experimental -b:a 192k -ac 2 salida.mp4
    ```
    
    FFmpeg comenzará a convertir el contenido del DVD en un archivo MP4. El progreso se mostrará en la terminal.
    
6. **Obtén el archivo MP4:** Una vez que la conversión esté completa, tendrás un archivo MP4 llamado "salida.mp4" en el directorio actual (puedes cambiar el nombre según tus preferencias). Este archivo contendrá el contenido del DVD convertido al formato MP4.
    

Es importante destacar que la conversión de un DVD a MP4 puede llevar tiempo, dependiendo de la duración y la calidad del contenido del DVD. Asegúrate de tener suficiente espacio en disco y paciencia para completar el proceso.