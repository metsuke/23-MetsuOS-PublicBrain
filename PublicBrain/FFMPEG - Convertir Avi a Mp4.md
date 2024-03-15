---
iaStatus: 0
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:30:55.000Z
modified: 2024-03-14T21:53:36.156Z
ver_major: 0
ver_minor: 1
ver_rev: 22
nav_primary: []
nav_secondary: []
tags: []
---
# FFMPEG - Convertir Avi a Mp4

[[PublicBrain/Index]]

Puedes utilizar la herramienta FFMPEG para convertir un archivo .avi a .mp4. FFMPEG es una potente utilidad de línea de comandos que permite manipular y convertir varios formatos de archivos multimedia. A continuación, te proporciono el comando que puedes utilizar:

```sh
ffmpeg -i 'archivo_entrada.avi' -c:v libx264 -c:a aac -strict experimental 'archivo_salida.mp4'
```

Aquí está una explicación de los parámetros utilizados:

- `-i archivo_entrada.avi`: Esto indica el nombre del archivo de entrada (archivo .avi que deseas convertir).
    
- `-c:v libx264`: Esto especifica el códec de video que se utilizará para la compresión en el archivo de salida. En este caso, estamos usando el códec H.264 (libx264) para el video.
    
- `-c:a aac`: Esto especifica el códec de audio que se utilizará para la compresión en el archivo de salida. En este caso, estamos usando el códec AAC para el audio.
    
- `-strict experimental`: Esto es necesario en algunos casos para habilitar códecs no estándar en FFMPEG.
    
- `archivo_salida.mp4`: Esto indica el nombre del archivo de salida (archivo .mp4 resultante de la conversión).
    

Simplemente reemplaza "archivo_entrada.avi" y "archivo_salida.mp4" con los nombres reales de tus archivos de entrada y salida, respectivamente. Ejecuta este comando en una terminal o ventana de línea de comandos en la carpeta donde se encuentren los archivos, y FFMPEG realizará la conversión de .avi a .mp4.

## En Hazel

Si deseas ejecutar el comando FFMPEG para convertir cada archivo .avi en un archivo .mp4, tomando el parámetro que pasa Hazel para cada archivo individual, aquí tienes cómo hacerlo:

1. Abre la aplicación Hazel en tu Mac.
    
2. Crea una nueva carpeta en algún lugar y coloca tus archivos .avi en ella.
    
3. En Hazel, crea una nueva regla para esa carpeta siguiendo estos pasos:
    
    - Selecciona la carpeta en la que colocaste los archivos .avi en la lista de carpetas monitoreadas.
    - Haz clic en el botón "+ Regla".
4. A continuación, define la regla:
    
    - En "Si todas las siguientes condiciones son verdaderas:", selecciona "Extensión" y luego "es" en el menú desplegable. Escribe "avi" en el campo de texto.
        
    - En "Realizar las siguientes acciones:", selecciona "Ejecutar script" y elige "bash" como lenguaje de script.
        
    - Ingresa el siguiente script en el área de script:
        
  
```sh
archivo_avi="$1" 
archivo_mp4="${archivo_avi%.avi}.mp4" 
ffmpeg -i "$archivo_avi" -c:v libx264 -c:a aac -strict experimental "$archivo_mp4"
```
        
5. Haz clic en "Guardar" para guardar la regla.
    

Con este enfoque, cada vez que coloques un archivo .avi en la carpeta monitoreada, Hazel pasará automáticamente el archivo .avi como un parámetro al script, y el script utilizará ese parámetro para generar el nombre del archivo .mp4 resultante. El archivo .avi original no se eliminará en este caso.

Ten en cuenta que, aunque el script no tiene un bucle, Hazel ejecutará el script por separado para cada archivo .avi que coloques en la carpeta.



