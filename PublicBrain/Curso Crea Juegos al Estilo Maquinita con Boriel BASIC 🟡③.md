---
iaStatus: 8
iaStatus_Model: Grok-3, Raúl Carrillo aka Metsuke
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: "2"
checked: 0
lang: ES
translations: 
created: 2025-07-08T04:18:38.438Z
modified: 2025-07-08T18:24:02.042Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Curso Crea Juegos al Estilo Maquinita con Boriel BASIC 🟡③


![Crea Juegos al Estilo Maquinita con Boriel BASIC](PublicBrain/_resources/6b34c91f2e36ec6d8e57b99c11c6e22d_MD5.jpg)

[[Aprender a desarrollar videojuegos  ⚫①]]

¡Bienvenidos a un apasionante viaje al corazón de la nostalgia! Este curso te invita a redescubrir la magia de las **maquinitas** —esas pequeñas joyas electrónicas como **Game & Watch**, **Tronica** o los coloridos **Jungler**, **Popeye** y **Defender**— y a crear tus propios juegos inspirados en ellas usando **Boriel BASIC** en el **ZX Spectrum**. 

No importa si nunca has programado o si el ZX Spectrum es un desconocido para ti: esta guía está pensada para principiantes y amantes del retro por igual. Desde explorar la historia de estas máquinas icónicas hasta construir un juego completo con múltiples pantallas, gráficos vibrantes y mecánicas adictivas, te guiaremos paso a paso con ejemplos prácticos, ejercicios y un proyecto final que podrás compartir con el mundo.

Vamos a diseñar y programar juntos un juego completo que capture la esencia de las maquinitas LCD, con gráficos monocromáticos o en color, usando un emulador de ZX Spectrum. Solo necesitas un ordenador, curiosidad y entusiasmo. ¡No se requiere experiencia previa!

## Introducción: La Magia de las Maquinitas

- **¿Qué eran las maquinitas?**
    - **Game & Watch (Nintendo, 1980-1991)**: Dispositivos portátiles con pantallas LCD monocromáticas, diseños compactos y jugabilidad sencilla que cautivaron a millones.
    - **Tronica y otras marcas**: Variaciones con temáticas únicas, como **Shuttle Voyage** o **Monkey Jump**, que ofrecían experiencias similares.
    - **Maquinitas en color**: Títulos como **Jungler**, **Popeye** y **Defender**, que añadían paletas limitadas para un toque visual más vibrante.
    - **Impacto cultural**: Cómo estas máquinas definieron la portabilidad, la simplicidad y la nostalgia en los videojuegos.
- **Por qué el ZX Spectrum es perfecto para recrearlas**
    - Similitudes: Hardware limitado y estética retro que evocan los 80.
    - Ventajas de **Boriel BASIC**: Un lenguaje moderno y eficiente para programar en el ZX Spectrum.
- **Qué conseguiremos**
    - Un motor reutilizable para crear juegos al estilo maquinita.
    - Un juego completo con múltiples pantallas, monocromo o en color, listo para compartir.

## Capítulo 1: Descubriendo el ZX Spectrum

- **1.1 Un icono de los 80**
    - El lanzamiento del ZX Spectrum en 1982 y su impacto en Europa.
    - Modelos principales: 48K y 128K, y sus diferencias.
- **1.2 Cómo funciona el ZX Spectrum**
    - Pantalla: 256x192 píxeles, dividida en 32x24 caracteres.
    - Colores: 8 tonos y el desafío del _attribute clash_.
    - Sonido: El _beeper_ (48K) y el chip AY (128K).
- **1.3 Emuladores para revivir la magia**
    - Instalación de emuladores como Fuse y ZEsarUX.
    - Cargar programas en formatos .tap y .tzx.
- **1.4 Tus primeros pasos**
    - Configurar tu entorno: Un editor de texto y un emulador.
    - Ejercicio: Mostrar un mensaje en pantalla.

**Práctica**: Escribe un programa que muestre "¡Bienvenidos al ZX Spectrum!" y pruébalo en tu emulador de elección.

### Capítulo 2: Primeros Pasos con Boriel BASIC

- **2.1 ¿Qué hace especial a Boriel BASIC?**
    - Diferencias con el Sinclair BASIC: Más funciones, mejor rendimiento.
    - Por qué es ideal para crear juegos retro.
- **2.2 Preparando el entorno**
    - Descargar e instalar el compilador ZX BASIC desde boriel.com.
    - Cómo compilar tu primer programa a .tap.
- **2.3 Dominando lo básico**
    - Variables: UBYTE, UINTEGER y más.
    - Estructuras de control: "I"F, FOR, WHILE, SUB.
    - Comandos esenciales: PRINT, CLS, BEEP.
- **2.4 Tu primer programa**
    - Mostrar texto y añadir un pitido retro.
    - Ejercicio: Mover un carácter por la pantalla con teclas.

**Práctica**: Crea un programa que mueva un sprite (carácter ASCII) usando las teclas Q y A.

## Capítulo 3: Gráficos que Cautivan

- **3.1 La pantalla del ZX Spectrum**
    - Entender la resolución y los atributos de color (8x8).
    - Cómo lidiar con el _attribute clash_.
- **3.2 Creando sprites con UDG**
    - Diseñar gráficos 8x8 con POKE UDG.
    - Herramientas recomendadas: ZX-Paintbrush y UDG Editor.
- **3.3 Estilo monocromático (Game & Watch)**
    - Fondo negro y sprites blancos para imitar pantallas LCD.
    - Ejemplo: Una nave y un meteorito para "Space Escape".
- **3.4 Colores al estilo Jungler y Popeye**
    - Usar INK 1-7 para paletas vibrantes pero limitadas.
    - Ejemplo: Sprites de Popeye (verde, rojo) o Jungler (multicolor).
    - Trucos para minimizar el _attribute clash_.
- **3.5 Animaciones simples**
    - Cambiar UDG para simular movimiento.
    - Ejemplo: Un enemigo que parpadea.

**Práctica**: Diseña dos sprites UDG (jugador y obstáculo) y muéstralos en pantalla, uno monocromo y otro en color.

## Capítulo 4: Controles y Mecánicas Adictivas

- **4.1 Capturando las teclas**
    - Usar INKEY$ para leer teclas como Q, A o M.
    - Crear controles personalizables y fluidos.
- **4.2 Mecánicas al estilo maquinita**
    - Movimiento del jugador con límites en pantalla.
    - Objetos dinámicos: Generación aleatoria con RND.
    - Colisiones: Detectar cuándo dos sprites se tocan.
- **4.3 Puntuación y desafío**
    - Gestionar el puntaje con UINTEGER.
    - Aumentar la dificultad: Más velocidad o más objetos.
- **4.4 Ejemplo práctico**
    - Un juego simple de esquivar obstáculos, inspirado en **Game & Watch: Fire**.

**Práctica**: Programa un juego donde un personaje esquive objetos que caen, con un sistema de puntuación.

## Capítulo 5: Múltiples Pantallas, Múltiples Aventuras

- **5.1 El arte del "canvas de pantalla"**
    - Usar estados (screenState) para simular pantallas LCD.
    - Inspiración: Niveles de **Game & Watch** o escenas estáticas de **Tronica**.
- **5.2 Diseñando pantallas**
    - Crear la función DrawScreen para mostrar sprites y fondos según el estado.
    - Ejemplo: Pantalla 1 (esquivar), Pantalla 2 (disparar), Pantalla 3 (objetivo final).
- **5.3 Transiciones suaves**
    - Cambiar pantallas según puntaje o eventos.
    - Añadir animaciones: Parpadeo, limpieza de pantalla (CLS) y sonidos.
- **5.4 Colores vibrantes**
    - Adaptar pantallas para juegos como **Jungler** (nave multicolor) o **Popeye** (rescate).

**Práctica**: Crea un juego con dos pantallas (una monocroma, otra en color) que cambie al alcanzar 50 puntos.

## Capítulo 6: Sonidos que Transportan

- **6.1 El sonido del ZX Spectrum**
    - El _beeper_ (48K) y sus pitidos característicos.
    - El chip AY (128K) para efectos más ricos.
- **6.2 Sonidos al estilo maquinita**
    - Efectos para movimiento, colisiones y cambios de pantalla.
    - Ejemplo: Pitidos cortos para **Game & Watch**, melodías simples para **Popeye**.
- **6.3 Optimizando el sonido**
    - Evitar retrasos en el juego al usar BEEP.
    - Combinar sonidos con la lógica del juego.

**Práctica**: Añade sonidos a un juego existente para movimiento, colisión y victoria.

## Capítulo 7: Un Motor para Todas tus Maquinitas

- **7.1 Construyendo el motor**
    - Módulos clave: InitGame, DrawScreen, HandleInput, UpdateGame, ChangeScreen.
    - Variables globales para posiciones, puntaje y estado.
- **7.2 Personalización sin límites**
    - Cambiar sprites UDG para diferentes juegos.
    - Adaptar mecánicas: Esquivar, disparar, completar objetivos.
- **7.3 Monocromo y color**
    - Configurar INK/PAPER para **Game & Watch** o **Defender**.
    - Ejemplo: Un motor para un juego inspirado en **Jungler**.
- **7.4 Pruebas y mejoras**
    - Probar en emuladores como Fuse o ZEsarUX.
    - Corregir problemas como _attribute clash_ o ralentizaciones.

**Práctica**: Desarrolla un motor base y adáptalo para un juego con tres pantallas.
### Capítulo 8: Tu Propia Maquinita - Proyecto Final

- **8.1 Soñando el juego**
    - Elegir un concepto: **Game & Watch** (monocromo), **Tronica**, o en color (**Popeye**, **Defender**).
    - Diseñar tres pantallas con mecánicas y estética únicas.
- **8.2 Haciéndolo realidad**
    - Usar el motor del Capítulo 7.
    - Crear sprites UDG (monocromo o en color).
    - Añadir sonidos y transiciones fluidas.
- **8.3 Perfeccionando el juego**
    - Reducir parpadeos y optimizar rendimiento.
    - Ajustar la dificultad para que sea divertido.
- **8.4 Compartiendo tu creación**
    - Compilar el juego a .tap.
    - Publicar en itch.io.
    - Crear capturas o un vídeo para promocionarlo en X.

**Proyecto Final**: Un juego completo con tres pantallas, como "Space Defender" o "Fireman Rescue".

## Apéndices

- **A. Glosario**
    - Términos clave: UDG, _attribute clash_, .tap, BEEP, etc.
- **B. Herramientas recomendadas**
    - Enlaces a ZX BASIC, Fuse, ZEsarux, ZX-Paintbrush.

## Referencias Bibliográficas

### Fuentes que apoyan el contenido

1. **[Nintendo Co., Ltd. (2020). "Game & Watch: Super Mario Bros."  🌐🟡③](https://www.nintendo.com/es-es/Noticias/2020/noviembre/-Seis-secretos-sobre-la-consola-Game-Watch-Super-Mario-Bros--1875308.html)**
	 * Página oficial de Nintendo que detalla la reedición de Game & Watch, incluyendo su historia y características técnicas. Confirma el diseño compacto, pantallas LCD y jugabilidad simple.  
2. [Spectrum for Everyone / Technical 🌐🟡③](https://spectrumforeveryone.com/technical/)
	* Especificaciones técnicas detalladas del ZX Spectrum, que incluyen el procesador Zilog Z80A, la ULA (Uncommitted Logic Array), configuraciones de memoria (16K/48K/128K), pantalla (256x192 píxeles con colisión de colores o "attribute clash") y sonido (beeper y chip AY-3-8912 en modelos 128K). Ofrece información sobre el diseño y revisiones del hardware, útil para comprender la arquitectura técnica y las limitaciones del ZX Spectrum.
3. **[Boriel BASIC Documentation (2023). "ZX BASIC Compiler Documentation" 🌐🟡③](https://zxbasic.readthedocs.io/en/latest/)**  
    * Documentación oficial del compilador Boriel BASIC, que describe su sintaxis, optimización y uso en ZX Spectrum. Respalda los Capítulos 2 y 7 sobre programación y creación del motor. Verificado en el sitio oficial.  
4. **[Segura Durán, J. (2023).  Boriel Basic para ZX Spectrum: Manual para torpes...y para los que no lo son tanto](https://www.amazon.es/Boriel-Basic-para-ZX-Spectrum/dp/B0CQD65FXZ)**  
	* Libro en español que explica cómo usar Boriel BASIC para crear programas y juegos en ZX Spectrum, con ejemplos detallados de gráficos UDG, sprites, tiles y mecánicas de juego. Apoya los Capítulos 3, 4 y 7. Publicado de forma independiente. ISBN: 979-8-87154654-3  
### Fuentes que refutan o matizan el contenido

- **Ninguna fuente verificable disponible**.  
    
![[Plantilla - 1MT#One More Thing]]