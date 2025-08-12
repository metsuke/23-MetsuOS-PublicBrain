---
iaStatus: 8
iaStatus_Model: Raúl Carrillo Garrido aka metsuke
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-08-09T22:23:22.134Z
modified: 2025-08-10T17:28:00.278Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: 
nav_secondary: 
tags:
---
# Curso de ZXGM Básico 03 - Explorando la estructura general del motor 🟡③ 

![Estructura de ZXGM](PublicBrain/_resources/4dc9c9daf6e92425ff4724042d24a2b5_MD5.jpg)

* [[Curso de ZX Game Maker ⚫①]]
* [[Curso de ZXGM Básico 02 - Descarga e instalación del software 🟡③|<< Anterior]] | Siguiente >>

## Introducción

En este capítulo, nos enfocamos en lo mínimo que necesitas saber para crear un juego con ZX Game Maker (ZXGM): el launcher, la carpeta `assets` y la carpeta `examples`. 

Asumimos que ya instalaste ZXGM según [[Curso de ZXGM Básico 02 - Descarga e instalación del software 🟡③|el capítulo anterior]].

## Lo esencial para crear tu juego

La estructura de ZXGM es mas amplia que lo que te voy a contar aquí, pero se trata de simplificar tu trabajo al máximo, por lo que trataré de aportarte la mínima teoria imprescindible para lograr tu objetivo.

### 1. El Launcher (`zxsgm.py`)

![Interfaz de ZXGameMaker](PublicBrain/_resources/ea5edf6a0a50c5eae901d4a662e35336_MD5.jpeg)

El archivo `zxsgm.py`, ubicado en la carpeta raíz de ZXGM, es el script principal que lanza la interfaz gráfica del ZX Game Maker. Desde ahí podrás realiuzar las tareas básicas de compilación y algunas adicionales de comprobación, como previsualizar sprites de enemigos o el mapa del juego.

- **Cómo usarlo**:
    
    1. Abre una terminal y navega a la carpeta de ZXGM:
        
        ```bash
        cd /ruta/a/zx-game-maker
        ```
        
    2. Ejecuta el launcher:
        
        ```bash
        python zxsgm.py
        ```
        
    3. En la interfaz gráfica, selecciona el menú **Build > Game** para compilar el juego. Esto procesa los recursos y genera un archivo `.tap` en la carpeta `dist/`, listo para probar en un emulador de ZX Spectrum (como Fuse o ZEsarUX).
    4. Otras opciones del menú **Build**:
        - **Game (Verbose)**: Compila mostrando información detallada para depurar errores.
        - **FX**: Genera efectos de sonido si usas el reproductor de beeper.
- **Nota**: Asegúrate de que Python está instalado y en el PATH. Si ves errores, verifica los permisos de la carpeta o revisa la instalación de dependencias.
    
### 2. Carpeta `assets`

La carpeta `assets` contiene los recursos de tu juego (de hecho, si quieres hacer backup de tu juego, esta es la carpeta que debes conservar a buen recaudo):

- **`maps.tiled-project`**: Archivos de mapas creados con Tiled. Usa Tiled (versión 1.11.2 o superior) para diseñar los mapas de tu juego.
    
- **`tiles.zxp`**: Gráficos creados con ZX Paintbrush, respetando la resolución (256x192) y paleta (8 colores) del ZX Spectrum.
    
- **`sounds/`**: Archivos de audio para los pitidos del ZX Spectrum.
    
- **Cómo usarla**:
    
    - Configura en los parametros personalizados de tiled las diferentes opciones del juego (las veremos en un capítulo monográfico posterior).
    - Crea mapas en Tiled y guárdalos en `assets/`. 
    - Diseña gráficos en ZX Paintbrush y guárdalos como `.zxp` en `assets/`.
    - Usa el menú **Build > Game** para procesar estos archivos y generar el `.tap`.
### 3. Carpeta `examples`

La carpeta `examples` incluye proyectos de muestra para aprender cómo estructurar tu juego.

- **Cómo usarla**:
    1. Guarda tu juego (el contenido de la carpeta assets) en otro lugar, por ejemplo en assets_miJuego renombrando la carpeta.
    2. copia `examples/example-game/` a la carpeta raiz dentro de assets (creala si has renombrado la original)
    3. Abre `assets/maps.tiled-project` en Tiled y `assets/tiles.zxp` en ZX Paintbrush para ver cómo están hechos.
    4. Desde la carpeta raíz, ejecuta `python zxsgm.py`, luego selecciona **Build > Game** en la interfaz para compilar el juego de ejemplo.
    5. Carga el archivo `example-game.tap` (en `dist/`) en un emulador para probarlo.

En esencia la carpeta assets funciona como "ranura de cartucho" el juego que pongas ahi, será el que use Launcher.

## Conclusión

Con el launcher (`zxsgm.py`) y su menú **Build > Game**, la carpeta `assets` para mapas y gráficos, y la carpeta `examples` como referencia, tienes lo esencial para crear tu juego. En el próximo capítulo, empezaremos a identificar y perfilar los juegos (en plural) que usaremos como ejemplo.

## Referencias Bibliográficas

* Mis pruebas de campo ⚫① (En MacOS Ventura - Procesador Intel)
* [Documentación oficial del proyecto 🌐🟡③](https://gm.retrojuegos.org/index.html)
* [Repositorio de Github de ZX Game Maker 🌐🟡③](https://github.com/rtorralba/zx-game-maker) .
* [Página de Itch.io del proyecto 🌐🟡③](https://juntelart.itch.io/zx-game-maker)

![[Plantilla - 1MT#One More Thing]]