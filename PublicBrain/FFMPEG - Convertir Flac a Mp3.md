---
iaStatus: 0
iaStatus: 0
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:30:55.000Z
modified: 2024-03-13T14:33:29.723Z
ver_major: 0
ver_minor: 1
ver_rev: 21
nav_primary: []
nav_secondary: []
tags: []
---
# FFMPEG - Convertir Flac a Mp3

[[PublicBrain/Index]]

  
Para convertir archivos FLAC a MP3 utilizando FFmpeg, sigue estos pasos:

1. **Instala FFmpeg**: Si aún no tienes FFmpeg instalado, descárgalo e instálalo en tu sistema. Puedes obtener FFmpeg desde el sitio oficial: [https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)
    
2. **Abre una Terminal**: En tu sistema operativo, abre una terminal o línea de comandos.
    
3. **Navega a la Ubicación del Archivo**: Utiliza el comando `cd` para navegar a la ubicación del archivo FLAC que deseas convertir. Por ejemplo:
    
    ```sh
    cd /ruta/de/tu/archiv
    ```
    
4. **Realiza la Conversión**: Utiliza el comando `ffmpeg` para realizar la conversión. El siguiente comando es un ejemplo de cómo hacerlo:
    
```sh
ffmpeg -i archivo.flac -c:a libmp3lame -q:a 2 archivo.mp3
```
    
    En este comando:
    
    - `-i archivo.flac` especifica el archivo de entrada FLAC.
    - `-c:a libmp3lame` establece el códec de audio de salida como MP3 utilizando el códec `libmp3lame`.
    - `-q:a 2` define la calidad de audio del archivo MP3. El valor `2` es una buena calidad, pero puedes ajustarlo según tus preferencias (mayor número = menor calidad).
    - `archivo.mp3` es el nombre que le das al archivo de salida MP3.
5. **Ejecuta el Comando**: Presiona Enter para ejecutar el comando. FFmpeg comenzará a convertir el archivo FLAC a MP3.
    
6. **Espera a que Finalice**: El proceso de conversión puede llevar algún tiempo dependiendo del tamaño del archivo y la potencia de tu sistema.
    
| Valor `-q:a` | Descripción                     | Calidad de Audio | Tasa de Bits Objetivo | Tamaño de Archivo |
|--------------|---------------------------------|------------------|-----------------------|-------------------|
| 0            | Muy alta calidad                | Excelente        | Alta                  | Grande            |
| 1            | Excelente calidad               | Muy buena        | Alta                  | Grande            |
| 2            | Muy buena calidad               | Buena            | Moderada              | Moderado          |
| 3            | Buena calidad                   | Aceptable        | Moderada              | Moderado          |
| 4            | Calidad aceptable               | Aceptable        | Moderada              | Moderado          |
| 5            | Calidad promedio                | Aceptable        | Moderada              | Moderado          |
| 6            | Calidad ligeramente inferior    | Aceptable        | Moderada              | Moderado          |
| 7            | Calidad aceptablemente inferior | Aceptable        | Baja                  | Pequeño           |
| 8            | Calidad bastante inferior       | Aceptable        | Baja                  | Pequeño           |
| 9            | Muy baja calidad                | Pobre            | Muy baja              | Muy pequeño       |


Una vez finalizada la conversión, tendrás un archivo MP3 convertido en la misma ubicación que el archivo FLAC original. Asegúrate de ajustar los nombres de los archivos y las rutas según tus necesidades.