# FFMPEG - Convertir Flac a Mp3

[[Index]]

  
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
    

Una vez finalizada la conversión, tendrás un archivo MP3 convertido en la misma ubicación que el archivo FLAC original. Asegúrate de ajustar los nombres de los archivos y las rutas según tus necesidades.