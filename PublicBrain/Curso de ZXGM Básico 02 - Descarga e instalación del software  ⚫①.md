---
iaStatus: 8
iaStatus_Model: Grok-3, Raúl Carrillo aka Metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 
checked: 0
lang: ES
translations: 
created: 2025-08-03T09:28:28.444Z
modified: 2025-08-03T11:47:54.116Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Curso de ZXGM Básico 02 - Descarga e instalación del software  ⚫①

![Instalando ZXGM](PublicBrain/_resources/9631dcb41318e7af6a2f0ec170a515f6_MD5.jpg)

* [[Curso de ZX Game Maker ⚫①]]
* [[Curso de ZXGM Básico 01 - ¿Qué es ZX Game Maker? 🟡③|<< Anterior]] | Siguiente >>

> OJO WIP

En este segundo capítulo del curso básico de ZX Game Maker (ZXGM), aprenderás cómo descargar e instalar el software necesario para comenzar a desarrollar videojuegos para el ZX Spectrum. 

Este tutorial está diseñado para usuarios de todos los niveles, desde principiantes hasta aquellos con experiencia previa, y cubre los pasos para configurar el entorno en sistemas operativos modernos (Windows, macOS y Linux). 

Siguiendo estas instrucciones, tendrás un entorno funcional para empezar a crear tus propios juegos retro.

## Requisitos previos

Antes de comenzar, asegúrate de cumplir con los siguientes requisitos:

- **Sistema operativo**: Windows (10 o superior), macOS (10.13 o superior) o una distribución de Linux (como Ubuntu 20.04 o superior).
- **Espacio en disco**: Al menos 2 GB de espacio libre para el software y las herramientas asociadas.
- **Conexión a Internet**: Necesaria para descargar el software y las dependencias.
- **Permisos administrativos**: En algunos casos, se requieren permisos de administrador para instalar ciertas herramientas.
- **Herramientas recomendadas**: Aunque ZXGM permite flexibilidad, se recomienda usar ZX Paintbrush para gráficos y Tiled para diseño de mapas.

## Paso 1: Descarga de ZX Game Maker

ZX Game Maker es un proyecto de código abierto alojado en GitHub. Sigue estos pasos para obtener la última versión:

1. **Visita el repositorio oficial**: Accede al repositorio de ZX Game Maker en GitHub ([Enlace al reposotorio 🌐🟡③](https://github.com/rtorralba/zx-game-maker)). Si no está disponible, consulta la documentación oficial en el grupo de Telegram de ZXGM o en foros como Spectrum Computing.
2. **Descarga la versión más reciente**: Haz clic en el botón verde "Code" y selecciona "Download ZIP" para descargar el archivo comprimido. Alternativamente, si tienes Git instalado, puedes clonar el repositorio con el comando:
    
    ```bash
    git clone https://github.com/rtorralba/zx-game-maker.git
    ```
    
3. **Descomprime el archivo**: Extrae el contenido del archivo ZIP en una carpeta de tu elección (por ejemplo, `C:\ZXGM` en Windows o `~/zxgm` en macOS/Linux). 
4. 
> Si has clonado el repositorio, no necesitarás realizar este ultimo paso.

## Paso 2: Instalación de dependencias

ZX Game Maker requiere varias herramientas y lenguajes para funcionar correctamente. A continuación, se detalla cómo instalar cada una:

### 2.1. Python

Python es necesario para ejecutar los scripts que generan los juegos.

- **Windows/macOS**:
    
    1. Descarga la última versión de Python desde [python.org 🌐🟡③](https://www.python.org/downloads/).
    2. Ejecuta el instalador y asegúrate de marcar la opción "Add Python to PATH".
    3. Verifica la instalación abriendo una terminal y ejecutando:
        
        ```bash
        python --version
        ```
        
        Deberías ver la versión instalada (por ejemplo, Python 3.13.x).
- **Linux**:
    
    1. La mayoría de las distribuciones ya incluyen Python. Verifica ejecutando:
        
        ```bash
        python3 --version
        ```
        
    2. Si no está instalado, usa el gestor de paquetes de tu distribución, por ejemplo:
        
        ```bash
        sudo apt install python3 python3-pip
        ```
 

### 2.2. Tiled (Editor de mapas)

Tiled es una herramienta recomendada para crear mapas de juego.

> Se recomienda mínimo 1.11.2, ya que (a fecha 3 de Agosto de 2025) es la última versión estable que incluye mejoras significativas en soporte de .tiled-project, incorporado en ZX Game Maker a partir de Octubre de 2024.

1. Descarga Tiled desde [mapeditor.org 🌐🟡③](https://www.mapeditor.org/) 
2. Instala siguiendo las instrucciones del instalador para tu sistema operativo.
3. Abre Tiled para asegurarte de que funciona correctamente. No necesitas configurarlo aún; ZXGM incluye plantillas compatibles en la carpeta `assets`.

### 2.3. ZX Paintbrush (Editor gráfico)

ZX Paintbrush es ideal para crear gráficos que respeten las limitaciones del ZX Spectrum.

1. Descarga ZX Paintbrush desde su sitio oficial o desde un enlace proporcionado en la documentación de ZXGM.
2. Instala el programa. En Windows, es un ejecutable; en macOS/Linux, necesitarás usar [wine  🌐🟡③](https://www.winehq.org).
3. Abre ZX Paintbrush y verifica que puedes crear un archivo `.zxp`.

### 2.4. Otras dependencias

Algunas dependencias adicionales, como la librería el compilador de Boriel Basic o GuSprites, se incluyen en el repositorio de ZXGM y se cargarán automaticamente en tu carpeta al ejecutar la instalación de dependencias anteriormente descrita. Asegúrate de no modificar la carpeta `libs` dentro del proyecto descargado.

## Paso 3: Configuración del entorno

1. **Organiza la carpeta del proyecto**:
    - Asegúrate de que la carpeta descomprimida de ZXGM contiene las subcarpetas `assets`, `libs` y `dist`.
    - La carpeta `assets` incluye archivos como `maps.tiled-project` y `tiles.zxp` para configurar mapas y gráficos.
2. **Configura las variables de entorno (opcional)**:
    - En Windows, añade las rutas de Python y ZX Basic al PATH si no se configuraron automáticamente.
    - En macOS/Linux, verifica que los comandos `python3` y `zxb` sean accesibles desde la terminal.
3. **Prueba el entorno**:
    - Navega a la carpeta del proyecto en una terminal:
        
        ```bash
        cd /ruta/a/zx-game-maker
        ```
        
    - Ejecuta el script de prueba proporcionado (por ejemplo, `make-game-win bat` en Windows o `make-game.sh` en macOS/Linux).
    - Si no hay errores, se generará un archivo de juego en la carpeta `dist`.

## Paso 4: Verificación de la instalación

1. **Ejecuta un emulador de ZX Spectrum**:
    - Descarga un emulador como Fuse ([fuse-emulator.sourceforge.io  🌐🟡③](https://fuse-emulator.sourceforge.io/)) 
    - Carga el archivo generado en `dist` (por ejemplo, `game.tap`) en el emulador para verificar que funciona.
2. **Revisa el mapa de memoria**:
    - En la carpeta `dist`, encontrarás un archivo de mapa de memoria que detalla el uso de recursos. Úsalo para asegurarte de que el juego cumple con las limitaciones del ZX Spectrum (48k o 128k).

## Solución de problemas comunes

- **Python no encontrado**: Asegúrate de que Python está en el PATH y usa `python3` en Linux/macOS.
- **Errores de compilación**: Verifica que Boriel’s ZX Basic está instalado correctamente y que no hay dependencias faltantes.
- **Archivos no generados en `dist`**: Revisa los permisos de la carpeta y asegúrate de ejecutar el script correcto para tu sistema operativo.
- **Problemas con gráficos**: Confirma que los archivos `.zxp` y los mapas en Tiled cumplen con las restricciones de resolución y paleta del ZX Spectrum.

Para más ayuda, consulta el grupo de Telegram de ZXGM o los tutoriales en vídeo mencionados en la documentación oficial.

## Conclusión

Con ZX Game Maker y sus dependencias instaladas, estás listo para comenzar a crear videojuegos para el ZX Spectrum. En el próximo capítulo, seguiremos avanzando en nuestro aprendizaje. ¡Prepárate para dar vida a tus ideas!

## Referencias Bibliográficas

* Mis pruebas de campo ⚫① (En MacOS Ventura - Procesador Intel)
* [Documentación oficial del proyecto 🌐🟡③](https://gm.retrojuegos.org/index.html)
* [Repositorio de Github de ZX Game Maker 🌐🟡③](https://github.com/rtorralba/zx-game-maker) .
* [Página de Itch.io del proyecto 🌐🟡③](https://juntelart.itch.io/zx-game-maker)

![[Plantilla - 1MT#One More Thing]]