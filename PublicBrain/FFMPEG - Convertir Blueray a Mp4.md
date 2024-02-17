# FFMPEG - Convertir Blueray a Mp4

[[PublicBrain/Index]]

La conversión de un archivo de imagen de Blu-ray (archivo .iso) a un archivo MP4 utilizando FFmpeg puede ser un proceso más complejo que la conversión de un DVD, ya que los Blu-rays a menudo contienen contenido protegido por derechos de autor y su estructura es más compleja. Para realizar esta conversión, debes tener en cuenta los siguientes pasos generales:

1. **Instala FFmpeg:** Asegúrate de tener FFmpeg instalado en tu sistema. Puedes descargar FFmpeg desde el sitio web oficial ([https://www.ffmpeg.org/download.html](https://www.ffmpeg.org/download.html)) o utilizar un gestor de paquetes si estás en Linux.
    
2. **Descifra el Blu-ray (si es necesario):** Muchos discos Blu-ray están protegidos contra copias mediante cifrado. Debes utilizar una herramienta de descifrado para desproteger el contenido antes de poder convertirlo. Un ejemplo de herramienta es "MakeMKV".
    
3. **Extrae el contenido del Blu-ray:** Una vez descifrado, extrae el contenido del Blu-ray en una carpeta en tu disco duro. Puedes utilizar una herramienta de extracción como "MakeMKV" o "DVDFab" para hacerlo.
    
4. **Convierte el contenido a MP4:** Con el contenido del Blu-ray en una carpeta en tu disco duro, puedes usar FFmpeg para convertirlo a MP4. Debes navegar a la carpeta que contiene los archivos de video y utilizar un comando similar al siguiente:
    
    ```sh   
    ffmpeg -i video.m2ts -c:v libx264 -preset slow -crf 22 -c:a aac -strict experimental -b:a 192k -ac 2 salida.mp4
    ```
    
    - `video.m2ts` debe reemplazarse con el nombre del archivo de video principal del Blu-ray en la carpeta. Los Blu-rays contienen varios archivos de video en diferentes formatos, así que asegúrate de seleccionar el archivo de video correcto.
5. **Personaliza la conversión:** Puedes personalizar los parámetros de conversión según tus preferencias, como la calidad de video, la resolución, el códec de audio, etc.
    
6. **Inicia la conversión:** Ejecuta el comando de conversión en la carpeta que contiene el archivo de video principal del Blu-ray.
    
7. **Obtén el archivo MP4:** Una vez que la conversión esté completa, tendrás un archivo MP4 en la carpeta especificada. Este archivo contendrá el contenido del Blu-ray convertido al formato MP4.
    

Es importante mencionar que la conversión de discos Blu-ray puede ser un proceso largo y que, en algunos casos, podrías necesitar software adicional para descifrar y extraer el contenido del Blu-ray. Además, ten en cuenta las leyes de derechos de autor y las restricciones regionales al realizar la conversión de discos Blu-ray, ya que puede haber limitaciones legales en algunos casos.