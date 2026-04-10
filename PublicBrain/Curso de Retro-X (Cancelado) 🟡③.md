---
iaStatus: 8
iaStatus_Model: Grok-4, Raul Carrillo aka Metsuke
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-09-22T05:18:18.593Z
modified: 2026-04-10T21:58:28.983Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 8
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoRetroX000.mp4
---
# Curso de Retro-X (Cancelado) 🟡③

![Curso de RetroX](PublicBrain/_resources/439e1ce07b8da71e3efc938988a5ea7e_MD5.jpg)

* [[Aprender a desarrollar videojuegos  ⚫①]]
* [[Que es Retro-X  ⚫①]]

> Este curso queda cancelado debido al manifiesto abandono de la herramienta Retro-X, en su lugar nos movemos a [[Curso de ZX-DRAW 🔴②]]

Iniciamos hoy un curso sobre **Retro-X**, una aplicación para Windows de 32 bits abandonada en 2009, diseñada para la conversión, edición y gestión de gráficos para sistemas retro de 8 bits, como ZX Spectrum, SAM Coupé, Commodore 64 (C64), Atari XL/XE, Amstrad CPC, Sprinter 2000 y otros. El curso se fundamenta en fuentes verificadas, como el README de la versión Alpha 8, el sitio web archivado del desarrollador (LCD), repositorios como World of Spectrum y discusiones en foros especializados en retrocomputing.

Dirigido a entusiastas del **retrocomputing**, la preservación digital y el arte píxel, el curso tiene una duración estimada de **10 a 12 semanas**, con sesiones de 2 a 3 horas semanales que combinan teoría, práctica y proyectos. **Requisitos**: PC con Windows (compatible con XP/Vista; en sistemas modernos, usar modo compatibilidad o Wine para Linux/Mac). **Materiales**: Descarga del ZIP de Retro-X Alpha 8 (853 KB desde World of Spectrum), imágenes de muestra retro y emuladores como ZXSpin o Fuse para ZX Spectrum.

## Módulo 1: Introducción a Retro-X y al Retrocomputing

Este módulo inicial sumerge a los estudiantes en el contexto de Retro-X y el fascinante mundo del retrocomputing, sentando las bases para un aprendizaje práctico y motivador.

### Lección 1.1: "Historia y Contexto de Retro-X

Retro-X nació como un proyecto personal del desarrollador **LCD** (de origen austriaco) entre 2005 y 2006, evolucionando desde herramientas simples como **BMP2SCR** hasta convertirse en una suite multifuncional. Abandonada en su versión **Alpha 8** (2009, con solo un 15% de completitud), se planeó una beta con un IDE completo y código abierto, pero estos planes no se concretaron debido a problemas como spam y acoso en foros (2012). Inspirada en la **demoscene** y herramientas clásicas como **Deluxe Paint**, Retro-X buscaba preservar y crear gráficos para sistemas de 8 bits. Aunque herramientas modernas como **ZX Paintbrush** o **RetroArch** ofrecen alternativas más actualizadas, Retro-X destaca por su soporte único a modos gráficos no estándar, como los de alta resolución del Sprinter 2000.

### Lección 1.2: Fundamentos del Retrocomputing

El **retrocomputing** es un hobby apasionante que implica restaurar, emular o programar para sistemas informáticos antiguos, como el **ZX Spectrum**, **SAM Coupé** o **C64**. Retro-X soporta una amplia gama de plataformas:

- **ZX Spectrum** (modos estándar e hires ASCII).
- **SAM Coupé** (modos 1-4).
- **C64** (hires y lowres).
- **Atari XL/XE** (Gr8, Gr9, Medres y overscan).
- **Amstrad CPC**, **Acorn**, **Timex**, **Sprinter 2000** (hires polychrome y lowres), **Amiga HAM6**, **GreyTV**, y **MSX** (parcial).
- Sistemas planeados: **Enterprise 128** y **Tandy CoCo**.

Su relevancia radica en la preservación histórica y en enseñar las limitaciones del hardware retro, como paletas de 15 a 71 colores o resoluciones de 256x192 píxeles.

### Lección 1.3: Instalación y Primeros Pasos

Descarga el ZIP de **Retro-X Alpha 8** desde World of Spectrum, extráelo y ejecuta el programa (no requiere instalación). Es compatible con entornos **Win32** (XP/Vista), con correcciones específicas para problemas como el parpadeo en Vista. En Windows modernos, activa el modo de compatibilidad; para Linux/Mac, usa **Wine**. La interfaz, desarrollada en **PureBasic 4.30**, está principalmente en inglés con traducciones parciales al alemán y se navega mediante pestañas y menús intuitivos. **Práctica**: Configura los directorios de guardado y carga las muestras incluidas para explorar la interfaz.

## Módulo 2: Componentes Principales - Converter

El **Converter** es el núcleo de Retro-X, ideal para transformar imágenes modernas en formatos retro con técnicas avanzadas de conversión.

### Lección 2.1: Introducción al Converter

El Converter permite convertir imágenes de PC (formatos como **BMP**, **PNG**, **AVI** o **GIF**) a estilos retro, utilizando técnicas como **dithering**, **error diffusion** y paletas adaptativas. Soporta modos básicos:

- **Bitonal monochrome**.
- **Greyscale** (SAM Mode 4).
- **Hires/lowres** para ZX, C64 y Atari.

En Alpha 8, se optimizaron procesos con **tablas LUT** (Look-Up Tables) para redraws ultrarrápidos (hasta 3100 por segundo en modos ZX Attr) y mejoras de velocidad del 20-60% en modos específicos.

### Lección 2.2: Técnicas Avanzadas de Conversión

Aprende a usar funciones de preprocesado como **flip**, **mirror** e **inversions**, junto con paletas adaptativas basadas en RGB (128,128,128). Novedades de Alpha 8:

- Modos para **Sprinter 2000** (hires/monochrome con solid, midtone, ordered y error diffusion).
- **Atari XL Gr9** (16 niveles de gris) y **Medres monochrome**.
- **Lowres Full Scan** (32x24 con 71 colores o 55 grises).
- Animaciones en formato **RXA** con paleta (Sprinter y Amiga HAM6) y un grabador de frames AVI optimizado para mayor velocidad.

### Lección 2.3: Correcciones y Limitaciones

Se resolvieron errores como el guardado rápido desde el portapapeles, la difusión de errores de color, fallos en escaneo y la selección inicial en modos hires. Sin embargo, persisten limitaciones:

- Tamaño máximo de pantalla libre (2 MB reservados).
- Ausencia de guardado en algunos modos nuevos.

## Módulo 3: Componentes Principales - Painter

El **Painter** es el editor de píxeles estrella de Retro-X, perfecto para crear y retocar gráficos con herramientas creativas y optimizadas.

### Lección 3.1: Interfaz y Herramientas Esenciales

El Painter ofrece un entorno de edición con:

- **Zoom** del 50-400% (controlado por rueda del ratón o botones 4-5).
- **Cuadrícula 8x8** y cursor en forma de cruz.
- **Zoom completo** (F9, inspirado en Deluxe Paint).
- Herramientas: **fill** (ignora bordes), cambio de atributos, **spline** (arcos con 4 puntos de control) y **genlock** (replace o blend, no disponible en todos los modos).
- Modos soportados: Spectrum hires/lowres, SAM 1-4 y Sprinter 2000 hires.

### Lección 3.2: Gestión de Objetos y Mapas

El **Object Manager** cuenta con una pestaña dedicada, permite importar archivos **RXO** mediante arrastre, exportar a **ASM** o portapapeles, y realizar manipulaciones como mirror, flip, invert o clear. El **Map Editor** (en fase inicial) incluye:

- Niveles de zoom (50-400%).
- Árbol de estructura y desplazamiento con el botón derecho del ratón.
- Autosnap para tiles y fuentes.

La integración permite guardar objetos y hasta 16 listas de tiles (con descarte de duplicados) en archivos RXO.

### Lección 3.3: Optimizaciones y Correcciones

Se mejoraron la velocidad de redraw (con genlock en Spectrum), la optimización de atributos y la detección de píxeles sin contornos en bordes. Correcciones incluyen:

- Fallos en fill para modos 16-bit.
- Atributos en áreas prohibidas.
- Parpadeo del cursor.
- Actualización tras cargar archivos RXS.


## Módulo 4: Componentes Principales - Viewer y Animaciones

Este módulo explora la visualización y reproducción de gráficos y animaciones retro, con un enfoque en la experiencia dinámica.

### Lección 4.1: Visualización Básica

El **Viewer** soporta formatos como **SCR**, **RXA**, **streams TAP**, **VID** (parcial para SymbOS) y **GIF** (limitado a 16/256 colores). Ofrece:

- Zoom dinámico (teclas +/- o ratón).
- Menús emergentes.
- Reproducción con doble clic.

### Lección 4.2: Reproducción Avanzada

Para animaciones **RXA**, permite ajustar el tamaño de la ventana y recordar posiciones. Incluye funciones como chequeo de **GreyTV** y reproductores para TAP o VID SymbOS (limitados por falta de muestras). Se activaron todos los filtros en **PureBasic 4.30**.

### Lección 4.3: Práctica y Limitaciones

**Ejercicio**: Visualiza una animación RXA de Sprinter y convierte un AVI a stream TAP. **Limitación**: Los GIF grandes no se cargan (se recomienda usar PNG u OLE).

## Módulo 5: Componentes Avanzados - Disc Master, XIDE, Object Manager y Font Editor

Profundizamos en herramientas especializadas para gestionar discos, editar código y trabajar con fuentes.

### Lección 5.1: Disc Master

El **Disc Master** gestiona imágenes de disco (+D, MGT, SCL) con:

- Buscador de datos (spin-gadget para ancho).
- Desensamblador.
- Detector de imágenes duplicadas (lectura optimizada).
- Soporte para contenedores SCL (muestra pantallas).
- Filtros de nombres (ej. "cover").

Correcciones: creación de MGT y mejora en la interpretación de bytes. **Práctica**: Carga un contenedor SCL y busca imágenes duplicadas.

### Lección 5.2: XIDE

El **XIDE** es un prototipo básico en Alpha 8, con planes para una beta con multivista, resaltado de sintaxis, autocompletado y plegados. Funciones actuales:

- AutoREM/UnREM personalizable ("Rem" o "'").
- Corrección: no elimina la última línea.

**Práctica**: Edita un código Z80 simple para usar con **ZXB-Compiler**.

### Lección 5.3: Object Manager y Font Editor

- **Object Manager**: Integrado con Painter, permite alternar atributos, máscaras y compresión, gestionar hasta 16 listas de tiles y realizar ediciones (mirror, flip, invert, export, atributos).
- **Font Editor**: Exporta a ASM/portapapeles, ofrece undo limitado (una acción, solo operaciones), actualiza la vista previa al pintar e importa fuentes PC (arreglado crash).
## Módulo 6: Funciones Varias y Optimizaciones

Este módulo revisa mejoras generales y tareas pendientes para entender el alcance de Alpha 8.

### Lección 6.1: Compressor y Manejo de ASM

El compressor corrige el fallo de ignorar el último byte de atributos y gestiona correctamente el truncado de cadenas ASM.

### Lección 6.2: Mejoras Generales en Alpha 8

- Cambio a **PureBasic 4.30** para acelerar la visualización de texto y hexadecimal.
- Refactorización del proceso "guardar como" para reducir el uso de memoria.
- Correcciones: guardado de RGB/ASC, memorización de TZX y fallo en importación de fuentes.

### Lección 6.3: Errores Conocidos y Tareas Pendientes

- **Errores**: Límite en NView para GIF grandes; funciones incompletas.
- **Pendientes**: Soporte para presión de tableta, paletas fading, exportación a palette/Basic, interrupciones SAM, RMI CPC, archivos SymbOS, modos Enterprise/MSX2+/Tandy, XIDE completo, soporte para discos reales Spectrum+. **Próximo**: Gestor de paletas.

## Módulo 7: Proyectos Prácticos y Aplicaciones

Pon en práctica lo aprendido con proyectos que integran las herramientas de Retro-X.

### Lección 7.1: Proyecto Básico - Conversión y Edición de una Pantalla ZX

Convierte una fotografía a formato **SCR**, edítala en el Painter y visualízala en el Viewer.

### Lección 7.2: Proyecto Avanzado - Animación RXA para SAM Coupé

Graba frames de un archivo AVI, aplica error diffusion y reproduce la animación resultante.

### Lección 7.3: Integración con Emuladores y Demoscene

Exporta gráficos a **ASM** para **Boriel's Basic** y utilízalos en emuladores como **Fuse** (ZX Spectrum) o **SimCoupé** (SAM Coupé). Crea assets para un juego homebrew sencillo.

## Módulo 8: Conclusión y Recursos Avanzados

Cerramos el curso con reflexiones y recursos para seguir explorando el retrocomputing.

### Lección 8.1: Limitaciones y Alternativas

Retro-X fue abandonado en 2012 debido a spam y acoso en foros, quedando limitado por su estado alpha. Alternativas modernas incluyen **ZX Paintbrush**, **CharPad** para C64 o **Aseprite** con paletas retro, que ofrecen soporte activo y mayor compatibilidad.

### Lección 8.2: Comunidad y Preservación

Participa en comunidades como **World of Spectrum**, **CPCWiki** o el subreddit **r/retrogamedev**, y asiste a eventos como **Forever**. Contribuye reportando bugs históricos o adaptando Retro-X a entornos modernos.

## Referencias Bibliográficas que Apoyan el Contenido

Las siguientes fuentes, verificadas y contrastables, confirman la existencia, características y contexto de Retro-X:

1. [Grussu, Alessandro (2022). _Spectrumpedia - English Edition - Volume 1_. Idra Editing Srl. ISBN: B0BQ9RQV5M 🌐 🟡③](https://spectrumcomputing.co.uk/entry/2001471/Book/Spectrumpedia) .- Describe Retro-X como una herramienta clave para conversión de gráficos ZX, destacando su rol en la preservación.
2. [World of Spectrum (2025). Archivo de utilidades para ZX Spectrum 🌐🟡③](https://worldofspectrum.net/utilities/) .- Con descarga de Retro-X Alpha 8 (853 KB), Valida la disponibilidad y descripción de Retro-X como suite de conversión y edición.
3. [LCD (2010). Sitio web archivado de Retro-X 🌐🟡③](https://web.archive.org/web/20100201000000/http://members.inode.at/838331/retrox.html) .- Confirma características como Painter, Converter y el estado alpha, coincidiendo con el README que acompaña a la App.
4. [The Retro Collective (2015) "How to make ZX Spectrum graphics on a PC" 🌐🟡③](https://www.youtube.com/watch?v=-RgjyezdsqU)) .- Explica el uso de herramientas como Retro-X para crear gráficos Spectrum en PC, apoyando su relevancia histórica.

## Referencias Bibliográficas que Refutan el Contenido

> WIP: Revisando fuentes

Estas fuentes, también verificadas, cuestionan la relevancia o vigencia de Retro-X al destacar alternativas más modernas y mantenidas:

1. [Wikipedia (2025). "ZX Spectrum graphic modes" 🌐🟡③ 🟡③🌐 🟡③🌐](https://en.wikipedia.org/wiki/ZX_Spectrum_graphic_modes) .- The page describes the ZX Spectrum's standard graphic mode with 256x192 pixels and attribute-based coloring, various extended modes like hi-colour and ULAplus, and tools for graphics including Image to ZX Spec, Retro-X, and ZX GIMP plug-in.
2. [**Reddit r/zxspectrum (2017).** "Any suggestions for an art utility to create Spectrum graphics?". 🟡③🌐 🟡③🌐](https://www.reddit.com/r/zxspectrum/comments/65ov7a/any_suggestions_for_an_art_utility_to_create/) .- The Reddit thread from 2017 asks for PC art utilities for ZX Spectrum graphics in AGD game development, with a recommendation for ZX-Paintbrush.
3. [**Visual Studio Marketplace (2023).** "ZX Graphics Editor" por DuefectuCorp. 🟡③🌐 🟡③🌐](https://marketplace.visualstudio.com/items?itemName=DuefectuCorp.zxgraphics) .- The page details a Visual Studio Code extension for editing ZX Spectrum UDGs, fonts in .udg, .gdu, .fnt formats, with features like rotation, export to .tap/.bas, last updated April 2023.
4. [Spriteworx (2019). "Getting started with ZX Paintbrush and AGDx"  YouTube 🟡③🌐](https://www.youtube.com/watch?v=IOUE6biouNk) .- The YouTube video from September 2019 by Happy Coding tutorials basic tools in ZX Paintbrush for ZX Spectrum sprites and graphics, and importing into AGDx.


![[Plantilla - 1MT#One More Thing]]