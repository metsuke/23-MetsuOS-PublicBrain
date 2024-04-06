---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:30:55.000Z
modified: 2024-04-03T20:19:14.675Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 23
nav_primary: []
nav_secondary: []
tags: []
---
# FFMPEG - Convertir M4v a Mp4

[[PublicBrain/Index]]

Para convertir un archivo M4V a MP4 utilizando la herramienta de línea de comandos FFmpeg, puedes seguir los siguientes pasos:

1. **Instala FFmpeg**: Si aún no tienes FFmpeg instalado, debes descargarlo e instalarlo en tu sistema. Puedes obtener FFmpeg desde el sitio oficial: [https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)
    
2. **Abre una Terminal**: En tu sistema operativo, abre una terminal o línea de comandos.
    
3. **Navega a la Ubicación del Archivo**: Utiliza el comando `cd` para navegar a la ubicación del archivo M4V que deseas convertir. Por ejemplo:
    
```sh
cd /ruta/de/tu/archivo
```
    
4. **Realiza la Conversión**: Utiliza el comando `ffmpeg` para realizar la conversión. El siguiente comando es un ejemplo de cómo hacerlo:
    
```sh
ffmpeg -i archivo.m4v -c:v copy -c:a copy archivo.mp4
```
    
    En este comando:
    
    - `-i archivo.m4v` especifica el archivo de entrada M4V.
    - `-c:v copy -c:a copy` indica que se debe copiar el flujo de video y audio sin realizar ninguna conversión.
    - `archivo.mp4` es el nombre que le das al archivo de salida MP4.
5. **Ejecuta el Comando**: Presiona Enter para ejecutar el comando. FFmpeg comenzará a convertir el archivo M4V a MP4.
    
6. **Espera a que Finalice**: El proceso de conversión puede tomar algún tiempo según el tamaño del archivo y la potencia de tu sistema.
    

Una vez que el proceso haya finalizado, tendrás un archivo MP4 convertido en la misma ubicación que el archivo M4V original. Recuerda que, dependiendo de los detalles específicos del archivo M4V y tus preferencias, es posible que necesites ajustar los parámetros de conversión para obtener los resultados deseados.