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
created: 2025-09-16T05:58:01.765Z
modified: 2026-04-10T21:56:18.841Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 8
nav_primary: []
nav_secondary: []
tags: []
---
# Curso de ZXGM Básico 07 - Creando nuestros Tiles 🟡③

![Cursp ZXGM Los tiles](PublicBrain/_resources/87474c7281eab0f536fa358c6b04c8e2_MD5.jpg)

* [[Curso de ZX Game Maker ⚫①]]
* [[Curso de ZXGM Básico 06 - Pantallas de presentación y transición en el juego 🔴②|<< Anterior]] | Siguiente >>

Hoy nos sumergimos en el apasionante mundo de los tiles, esos bloques fundamentales que dan forma a los escenarios de tus juegos retro. 

Si eres nuevo en el desarrollo para ZX Spectrum, no te preocupes: vamos a desgranarlo paso a paso de manera clara y práctica. 

En esta sección, aprenderás qué son los tiles, cómo se estructuran en el tileset del ZX Spectrum Game Maker, y, sobre todo, cómo editarlos con ZX Paintbrush para personalizar tus creaciones. Al final, tendrás las herramientas para construir niveles vibrantes y funcionales, respetando las limitaciones del hardware clásico del ZX Spectrum.

## ¿Qué Son los Tiles?

Los tiles son, en esencia, pequeños cuadrados de 8x8 píxeles que actúan como bloques de construcción para los escenarios de tus juegos. En el contexto de ZX Spectrum y herramientas como [[Tutorial d'AGD 2018 Capítol 02 - Què són els tiles ⚫①|AGD (Arcade Game Designer)]] o ZX Spectrum Game Maker, representan elementos como paredes, suelos, plataformas o decoraciones. 

Cada tile no solo lleva un patrón gráfico, sino también atributos como colores (limitados a dos por tile: ink para el foreground y paper para el background), brillo (bright) y parpadeo (flash), lo que optimiza el uso de la memoria limitada del ZX Spectrum (solo 48K o 128K). 

Esto permite reutilizar tiles para componer pantallas enteras de forma eficiente, evitando dibujar todo pixel a pixel y reduciendo el consumo de recursos.

Por ejemplo, un tile podría ser un ladrillo sólido para una pared, o un fondo animado como agua. Su organización en un tileset (una imagen grande que agrupa todos) facilita el diseño en editores como Tiled, donde los colocas como piezas de un puzle. Esta aproximación es clave en juegos retro para lograr funcionamiento suave y colisiones precisas, aunque requiere planificación para evitar "color clash" (choque de colores cuando se superponen atributos). 

Si quieres profundizar en conceptos básicos, consulta [[Tutorial d'AGD 2018 Capítol 02 - Què són els tiles ⚫①|el tutorial sobre AGD]], que explican tiles como "los cuadraditos que sirven para diseñar las pantallas".

## Estructura del Tileset en ZX Spectrum Game Maker

El tileset en ZX Spectrum Game Maker es una imagen compacta de 256x48 píxeles, guardada en el archivo `assets/tiles.zxp`. Se divide en 256 tiles individuales de 8x8 píxeles, cada uno con un rol predefinido por el motor del juego. Esta estructura fija asegura comportamientos automáticos, como colisiones o interacciones, pero obliga a respetar el orden para evitar errores. Basado en la documentación oficial, aquí va un desglose secuencial y amigable:

> Ojo: WIP Comprobación

1. **Tile 0: Fondo (Background)**  .- Reservado para áreas neutras o vacías. El protagonista se mueve libremente sobre él, sin bloqueos. Úsalo para cielos o suelos básicos.
2. **Tiles 1 a 63: Sólidos (Solid)**  .- Ideales para obstáculos impenetrables como paredes o barreras. Incluyen variantes especiales:  
	   - Tile 61: Puerta que se abre con llave (solo pasa si el jugador tiene una).  
	   - Tile 62: Tile rompible (se destruye si activas la opción en las configuraciones).  
	   - Tile 63: Puerta que se abre al eliminar todos los enemigos de la habitación (con "shouldKillEnemies" habilitado).
3. **Tiles 64 y 65: Plataformas Traspasables desde Arriba** .- El personaje cae sobre ellas, pero no puede subir desde abajo. Perfectas para saltos descendentes.
4. **Tiles 66 y 67: Plataformas Bidireccionales**  .- Traspasables tanto desde arriba como desde abajo, como puentes flotantes para movimiento fluido.
5. **Tiles 68 y 69: Plataformas Traspasables solo desde Abajo** .- Permiten subir, pero no caer. Geniales para ascensos controlados.
6. **Tiles 70 a 73: Escaleras** .- Facilitan el movimiento vertical, simulando subidas y bajadas naturales.
7. **Tiles 74 a 250: No Sólidos (Non-Solid)** .- Pasables sin bloqueos, pero personalizables: añade daño (pinchos, fuego) o animaciones (agua, llamas). Su flexibilidad es ideal para entornos dinámicos.
8. **Tiles 251 a 255: Tiles Especiales para Objetos** .- Definidos en Tiled para items interactivos como coleccionables, power-ups o triggers. Adquieren colores del entorno para integrarse (su funcion se define en Tiled).

Recuerda: el formato .zxp es clave porque almacena no solo píxeles, sino atributos ZX-specific como ink/paper, evitando pérdidas al exportar.

## Cómo Editar el Tileset con ZX Paintbrush

Editar tiles con ZX Paintbrush es sencillo y potente, ya que está diseñado específicamente para ZX Spectrum. Esta herramienta gratuita maneja los atributos únicos del hardware: cada tile de 8x8 usa solo dos colores (ink para trazos, paper para fondo), más bright (brillo) y flash (parpadeo). Aquí va un guía paso a paso, basada en tutoriales prácticos:

1. **Instalación y Apertura**: Instala ZX-Paintbrush. Abre el archivo `tiles.zxp` desde `assets/` (o crea uno nuevo). La interfaz muestra una cuadrícula de 8x8 para cada tile.

2. **Entendiendo los Colores**: Selecciona ink (foreground) y paper (background) de la paleta de 15 colores ZX. Al pintar, el programa sustituye colores existentes: si cambias ink de blanco a azul, todo el ink blanco se actualiza. Evita "color clash" probando en emuladores.

3. **Herramientas Básicas**: Usa lápiz, borrador, relleno o copiar/pegar para diseñar. Para animaciones, dibuja frames consecutivos (ej. tile 74 y 75 para agua). Activa bright/flash en la barra de atributos para efectos visuales.

4. **Importar/Exportar**: "I"mporta imágenes BMP/PNG, pero ajusta manualmente a 8x8 y atributos ZX. Guarda como .zxp para que Tiled lo detecte automáticamente. Prueba cambios en el emulador para ver colisiones y animaciones.

5. **Consejos Prácticos**: Empieza con el tileset de ejemplo. Si editas sólidos, respeta posiciones para no alterar comportamientos. Para tiles animados, limita a 10 por pantalla para rendimiento. Si importas desde otros programas, convierte a formato ZX para evitar distorsiones.

ZX Paintbrush es ideal porque preserva datos que PNG no puede (como ink/paper), haciendo la edición retro-friendly. Estoy preparando un [[Curso de ZX-Paintbrush - Creación de Gráficos para ZX Spectrum (Cancelado)  🟡③|Curso de ZX-Paintbrush]], pero si necesitas ya un tutorial, busca guías en YouTube para "ZX Paintbrush basics".

## Recomendaciones para Tu Proyecto

Usa el tileset skeleton del proyecto como base: edítalo respetando la estructura para integración sencilla con Tiled. Experimenta con animaciones en no-sólidos para efectos extra, pero optimiza para 48K. 

¿Listo para el siguiente capítulo? ¡Prueba creando un nivel simple y comparte tus progresos!

## Referencias que Apoyan el Contenido

Estas fuentes validan la estructura de tiles, edición con ZX Paintbrush y conceptos generales. 

* Mis pruebas de campo ⚫①
* [Documentación oficial del proyecto 🌐🟡③](https://gm.retrojuegos.org/index.html)
* [Repositorio de Github de ZX Game Maker 🌐🟡③](https://github.com/rtorralba/zx-game-maker) .
* [Página de Itch.io del proyecto 🌐🟡③](https://juntelart.itch.io/zx-game-maker)
- [Instalación de ZX Paintbrush en ZX Spectrum Game Maker (2024) 🟡③🌐](https://gm.retrojuegos.org/mydoc_install_image_editor.html) .- Explica por qué usar .zxp para tiles y atributos (ink/paper), y su integración con el tileset.
- [Tutorial ZX Paintbrush en ZX Spectrum Game Maker (2024) 🟡③🌐](https://gm.retrojuegos.org/mydoc_zx_paintbrush.html) .- Guía básica sobre edición de tiles 8x8, colores ink/paper y peculiaridades ZX.
- [ZX Spectrum Game Maker Overview (2023, actualizado 2025) 🟡③ 🌐](https://gm.retrojuegos.org) .- Confirma tiles como "cuadraditos para diseñar pantallas" y uso de ZX Paintbrush.
- [Imágenes Base y Pantallas en ZX Spectrum Game Maker (2024) 🟡③🌐](https://gm.retrojuegos.org/mydoc_images_screens.html) .- Detalla edición de tilesets con ZX Paintbrush para pantallas.
- [ZX Spectrum Game Maker en itch.io** (2023, actualizado) 🟡③ 🌐](https://juntelart.itch.io/zx-game-maker) .- Herramienta visual con Tiled y ZX Paintbrush para tiles. 

## Referencias que Refutan o Corrigen Aspectos del Contenido

Aunque el enfoque de ZX Spectrum Game Maker es consistente, algunas fuentes cuestionan su rigidez (tiles fijos) frente a métodos más flexibles en ASM o engines alternos, o corrigen detalles como importación de imágenes. No hay refutaciones directas masivas, pero estas destacan limitaciones.

- [Tutorial ZX-Paintbrush y BIFROST en World of Spectrum** (2012, vigente 2025) 🟡③ 🌐](https://worldofspectrum.org/forums/discussion/40773/tutorial-zx-paintbrush-and-bifrost) .- Muestra edición de tiles multicolores no estándar en ZX Paintbrush, refutando la limitación estricta a 2 colores por tile en setups básicos.
- [Foro z88dk: RAGE1 Engine para ZX Spectrum (2023, activo) 🟡③ 🌐](https://z88dk.org/forum/viewtopic.php?t=11442) (Requiere cuenta de usuario gratuita) .-  Propone tiles dinámicos sin estructura fija, criticando la secuencialidad de sólidos/plataformas como restrictiva. 
- [Vídeo: Spectrum Next Tilemaps (YouTube, 2020) 🟡③ 🌐](https://www.youtube.com/watch?v=Yl-rak1A4A0) .- Usa formatos flexibles sin .zxp, refutando dependencia de ZX Paintbrush para tiles avanzados. 
- [Blog: "How To Write ZX Spectrum Games (2012, actualizado) 🟡③ 🌐](https://chuntey.wordpress.com/2012/12/18/how-to-write-zx-spectrum-games-chapter-1/) .- Enfatiza ASM sin tiles fijos, corrigiendo la simplificación de ZX Game Maker como no óptima para memoria. 
- [Foro Spectrum Computing: Moving Sprites** (2018, vigente)](https://spectrumcomputing.co.uk/forums/viewtopic.php?t=554&start=20) .- Recomienda herramientas alternativas a ZX Paintbrush para exportar bytes, cuestionando su enfoque para juegos complejos.

![[Plantilla - 1MT#One More Thing]]