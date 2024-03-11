---
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:30:55.000Z
modified: 2024-03-11T23:13:47.294Z
ver_major: 0
ver_minor: 1
ver_rev: 20
nav_primary: []
nav_secondary: []
tags: []
---
# FFMPEG - Convertir Aiff a Mp3

[[PublicBrain/Index]]

Para convertir archivos de audio de formato AIFF a MP3 utilizando la herramienta de línea de comandos `ffmpeg`, puedes seguir estos pasos:

1. **Instalación de ffmpeg**: Si aún no tienes `ffmpeg` instalado en tu sistema, debes instalarlo. Los métodos de instalación varían según el sistema operativo que estés utilizando. Por ejemplo, en sistemas basados en Unix (como Linux) puedes usar el gestor de paquetes. En Windows, puedes descargar el ejecutable desde el sitio web de ffmpeg.
    
2. **Ejecución del comando**: Una vez que tengas `ffmpeg` instalado, abre una terminal o línea de comandos y navega hasta la ubicación donde se encuentra el archivo AIFF que deseas convertir. Luego, utiliza el siguiente comando para realizar la conversión:
    

´´´sh
	ffmpeg -i entrada.aiff -c:a libmp3lame -q:a 2 salida.mp3
´´´

Explicación de los parámetros:

- `-i entrada.aiff`: Especifica el nombre del archivo de entrada AIFF.
- `-c:a libmp3lame`: Indica que se utilizará el códec de audio `libmp3lame` para la compresión en formato MP3.
- `-q:a 2`: Establece la calidad de audio para la salida MP3. El valor puede estar en el rango de 0 (mejor calidad) a 9 (peor calidad), donde 2 es una buena opción para una relación calidad-tamaño de archivo adecuada.
- `salida.mp3`: Define el nombre del archivo de salida MP3.

Asegúrate de reemplazar `entrada.aiff` con el nombre del archivo AIFF que deseas convertir y `salida.mp3` con el nombre que desees para el archivo de salida en formato MP3. Una vez que ingreses el comando y presiones Enter, `ffmpeg` realizará la conversión y crearás un archivo MP3 a partir del archivo AIFF original.

Recuerda que los nombres de archivo y las ubicaciones deben coincidir con la estructura de tu sistema de archivos, por lo que puede ser necesario ajustar las rutas según sea necesario.