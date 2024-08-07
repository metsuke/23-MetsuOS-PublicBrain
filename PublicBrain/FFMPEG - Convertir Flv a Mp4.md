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
created: 2024-04-06T23:48:59.344Z
modified: 2024-06-10T15:26:26.921Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 29
nav_primary: 
nav_secondary: 
tags:
---
# FFMPEG - Convertir Flv a Mp4

[[PublicBrain/Index]]

Para convertir archivos FLV a MP4 utilizando FFmpeg, puedes seguir estos pasos en la línea de comandos de tu sistema operativo:

1. **Descarga FFmpeg:** Si aún no tienes FFmpeg instalado en tu sistema, necesitarás descargarlo e instalarlo. Puedes obtener FFmpeg en su sitio web oficial: [https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)
    
2. **Abre la línea de comandos:** Abre la línea de comandos en tu sistema operativo (Terminal en macOS y Linux, o Command Prompt en Windows).
    
3. **Navega a la ubicación del archivo FLV:** Utiliza el comando `cd` para navegar a la ubicación del archivo FLV que deseas convertir. Por ejemplo:
    
    bashCopy code
    
    `cd ruta/del/archivo`
    
4. **Ejecuta el comando FFmpeg:** Una vez en la ubicación correcta, puedes ejecutar el siguiente comando para realizar la conversión:
    
```sh    
ffmpeg -i archivo.flv -c:v libx264 -c:a aac archivo.mp4
```
    
    Explicación de los parámetros:
    
    - `-i archivo.flv`: Especifica el archivo de entrada FLV.
    - `-c:v libx264`: "I"ndica el códec de video a utilizar para la salida, en este caso, H.264 (libx264).
    - `-c:a aac`: Indica el códec de audio a utilizar para la salida, en este caso, AAC.
    - `archivo.mp4`: Nombre del archivo de salida MP4.
5. **Espera a que termine la conversión:** FFmpeg comenzará a convertir el archivo FLV a MP4. El tiempo de conversión dependerá del tamaño del archivo y de la potencia de tu sistema.
    

Una vez que la conversión esté completa, tendrás un archivo MP4 listo para reproducir. Por favor, ten en cuenta que estos comandos son indicativos y podrían variar según tu sistema operativo y la versión de FFmpeg que estés utilizando. Asegúrate de verificar la documentación de FFmpeg o los mensajes de ayuda del comando si encuentras algún problema.