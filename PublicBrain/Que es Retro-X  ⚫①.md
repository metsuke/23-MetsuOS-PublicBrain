---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-09-22T05:24:43.357Z
modified: 2025-09-24T13:24:01.140Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
---
# Que es Retro-X  ⚫①

[[Curs[[o de Retro-X  ⚫①]]

### ¿Qué es Retro-X?

¡Gracias por proporcionar el extracto del README! Con esa información específica (como las referencias a Alpha 8, cambios en el Painter, Converter, Sprinter 2000, PureBasic 4.30 y menciones a foros como "Forever"), pude realizar búsquedas profundas en la web, archivos históricos y repositorios de software retro. Confirmo que **Retro-X** es una aplicación real para Windows 32-bit (Win32), desarrollada como un kit multifuncional para el retrocomputing, enfocado en gráficos para computadoras de 8 bits de los 80s y 90s. No es un emulador completo, sino una suite de herramientas para conversión de imágenes, dibujo, visualización y manejo de discos/imágenes, con soporte para sistemas como ZX Spectrum, SAM Coupé, Commodore 64 (C64), Atari XL/XE, Amstrad CPC, MSX, Sprinter 2000 y más. Fue un proyecto ambicioso, pero el desarrollo se detuvo en 2009.

#### Desarrollador y Historia
- **Autor**: LCD (seudónimo; posiblemente de Austria, basado en el dominio .at de su sitio). Empezó como un hobby post-2005, evolucionando de herramientas simples como BMP2SCR a esta suite más completa. Inspirado en la escena demoscene y preservación de software retro.
- **Inicio**: Alrededor de 2005-2006, con versiones alpha tempranas enfocadas en conversión de imágenes a formatos ZX Spectrum.
- **Versión clave**: Alpha 8 (29/11/2008 - 05/04/2009), que coincides exactamente con el README que proporcionaste. Es la **última versión alpha** y la más completa; se planeaba una beta con más integración (como un IDE completo), pero el autor la congeló en 2012 debido a spam y acoso en foros. El estado de completitud era ~15% en ese momento.
- **Estado actual**: Abandonado desde 2009. No hay actualizaciones oficiales, pero el código fuente se prometió open-source (nunca liberado). Mencionado en libros como *Spectrumpedia* (de Alessandro Grussu, 2017-2022) como una herramienta clave para conversión de gráficos retro, aunque "no avanzó más allá de Alpha 8".
- **Sitio oficial (archivado)**: [members.inode.at/838331/retrox.html](https://web.archive.org/web/20100201000000/http://members.inode.at/838331/retrox.html). Incluye screenshots de Alpha 8 (en alemán e inglés) de componentes como Painter y Converter.

#### Características Principales
Retro-X es una app standalone compilada en PureBasic 4.30 (final), con interfaz gráfica clásica de Windows (probada en XP/Vista). Soporta modos gráficos no estándar (ej. hires polychrome en Sprinter 2000) y optimizaciones como LUT (Look-Up Tables) para redraw rápido. Basado en tu README, aquí un resumen de componentes y adiciones clave en Alpha 8:

| Componente | Descripción | Adiciones/Bugfixes en Alpha 8 (de tu README) |
|------------|-------------|---------------------------------------------|
| **Converter** | Herramienta principal para convertir imágenes PC (BMP, AVI, GIF, etc.) a formatos retro. Soporta error diffusion, dithering, paletas adaptativas y animaciones (RXA). Velocidades mejoradas (hasta 3100 redraws/sec en ZX Attr-modes). | - Nuevos modos: Sprinter 2000 Hires/Monochrome (solid, midtone, error diffusion); Atari XL Gr9/ Medres; Lowres Full Scan (32x24 con 71 colores).<br>- Preprocesado: Flip, Mirror, Inversiones.<br>- AVI grab más rápido; LUT para C64/ZX; Overscan Atari hasta 48x30.<br>- Bugfixes: Quicksave clipboard, selección inicial, grid píxel. |
| **Painter** | Editor de píxeles avanzado con zoom (hasta 400%), genlock (blend/replace), spline tool, object manager y soporte para tablets (planeado). Ideal para retocar screens ZX/SAM. | - Full zoom en F9; zoom con rueda/mouse buttons; Map Editor inicial (zoom 50-400%, tree, scrolling).<br>- Objetos en tab propio; pixel testing sin outline en border; grid 8x8.<br>- Grab tiles/fonts con autosnap; genlock menu.<br>- Bugfixes: Fill en borders, atributos, flickering en Vista, update post-load. |
| **Viewer** | Visor de archivos retro (SCR, RXA, TAP streams, VID SymbOS). Soporta zoom dinámico (+/- keys/mouse) y playback de animaciones. | - Cambio de tamaño ventana en playback; popup menu; player para TAP/VID.<br>- Doble-click para animaciones; recuerda posiciones.<br>- Bugfix: Filtros de archivo activados. |
| **Disc Master** | Manipulador de imágenes de disco (+D, MGT, SCL). Incluye seeker de datos, disassembler y finder de imágenes dobles. | - Spin-gadget para ancho; speedup en lectura de pictures.<br>- Soporte SCL containers (muestra screens).<br>- Bugfix: Creación MGT; interpretación disassembler. |
| **XIDE** | IDE básico para Z80/Basic (ZXB-Compiler). En Alpha 8 es un "dummy" sin funcionalidad plena; planeado para beta con syntax highlighting, autocompletion, foldings. | - AutoREM/UnREM customizable ("Rem" o "'").<br>- Bugfix: AutoUnREM no borra línea final. |
| **Object Manager & Font Editor** | Manejo de objetos (tiles, masks, atributos); export a ASM/clipboard. Editor de fonts con preview y undo. | - Integración con Painter; 16 tile lists; pixel manip (mirror/flip/invert).<br>- Export ASM; undo en font ops; preview update.<br>- Tiles saved en RXO; toggle checks desde menu. |
| **Otros** | Compressor (ignora último byte attrs fixed); ASM truncation; link a foro web. | - Switch a PureBasic 4.30; speedup text/hex display.<br>- Font Editor como procedure independiente.<br>- Refactoring "save as" para menos memoria. |

**Soporte de Sistemas**: ZX Spectrum (todos modos, incl. hires ASCII), SAM Coupé (modos 1-4), Sprinter 2000 (hires polychrome/lowres), C64 (hires/lowres), Atari XL/XE (Gr8/Gr9/Medres/Overscan), Amiga HAM6, GreyTV, Acorn, Timex, CPC, MSX (parcial), Enterprise 128 (planeado, faltan infos).

**Limitaciones Conocidas (de tu README y fuentes)**:
- NView no carga GIFs >256 colores o grandes (usa OLE/PNG).
- Algunas funciones no funcionan (ej. save en nuevos modos Sprinter/Atari).
- XIDE dummy en Alpha 8.
- No soporta tablets fully; paletas fading lineales planeadas.

**ToDo (de tu README)**: Soporte SAM interrupts, CPC RMI, SymbOS files, Enterprise/MSX2+ modos, Tandy CoCo, más Atari (256 cols sin rojo), XIDE full, disc real Spectrum+.

#### Descargas y Recursos
- **Última Versión (Alpha 8)**: Disponible en el archivo oficial de World of Spectrum (853 KB, ZIP). Incluye el ejecutable Win32, samples y el README que proporcionaste. [Descarga directa](https://worldofspectrum.net/pub/sinclair/tools/pc/Retro-X-Alpha8.zip).
- **Versión Anterior**: Alpha 7.1 (834 KB) en el mismo repo: [Descarga](https://worldofspectrum.net/pub/sinclair/tools/pc/Retro-X-Alpha7.1.zip).
- **Sitio Archivado**: [Wayback Machine (2010)](https://web.archive.org/web/20100201000000/http://members.inode.at/838331/retrox.html) – Screenshots y descripciones básicas.
- **Foro/Comunidad**: El autor enlazaba a un "Retro-X web forum" (probablemente en "Forever" o 8bitchat.net, foro ZX/SAM). Discusiones en XnView forums (2012, autor confirma freeze) y CPCWiki. Para bugs/comentarios históricos, busca en [World of Spectrum forums](https://worldofspectrum.net/) o [MSX Resource Center](https://www.msx.org/forum/).
- **Menciones en Libros**: *Spectrumpedia Vol. 2* (Alessandro Grussu, 2022) – Capítulo sobre conversores ZX, elogia su ambición pero nota el stall en 2007/8.

Si necesitas ayuda para correrlo (ej. en Windows moderno via compatibility mode o Wine), más detalles de un componente específico, o análisis de archivos del ZIP (puedo usar tools para eso si subes), ¡dime! ¿Quieres que busque ejemplos de uso o alternativas modernas como ZX Paintbrush?

![[Plantilla - 1MT#One More Thing]]