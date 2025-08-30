---
iaStatus: 8
iaStatus_Model: Raúl Carrillo Garrido aka metsuke
iaStatus_Generado: H
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-08-28T13:37:23.615Z
modified: 2025-08-28T15:15:11.100Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
---
# Curso de ZXGM Básico 06 - Pantallas de presentación y transición en el juego 🔴②



* [[Curso de ZX Game Maker ⚫①]]
* [[Curso de ZXGM Básico 05 - Calibrando funcionalidad y memoria para nuestro juego 🔴②|<< Anterior]] | Siguiente >>

> OJO WIP

En el capítulo de hoy, nos centraremos en las pantallas de presentación y transición de tu juego. Los detalles sobre cómo trabajar con ZX Paintbrush se tratarán en el [[Curso de ZX-Paintbrush - Creación de Gráficos para ZX Spectrum  ⚫①]], aquí nos enfocaremos en qué pantallas puedes incluir, dónde deben ubicarse y cómo gestionar el espacio en memoria que ocupan. Estas pantallas son esenciales para mejorar la experiencia del usuario, ofrecer retroalimentación visual y garantizar un juego pulido.

Básicamente, se parte de una imagen base, que puede ser creada por ti, por un artista profesional o, como haré en esta ocasión, generada mediante IA. Esta imagen se reduce al tamaño requerido en 1 bit (monocromo) con un programa de edición de imágenes, para luego ajustarla manualmente y colorearla según las limitaciones gráficas del ZX Spectrum.
## Las Pantallas Obligatorios

### Carga (Loading Screen)

En Cursed Castilla, partiremos de esta imagen:

![Caratula de Cursed Zapatillas](PublicBrain/_resources/33d90a6b2fb87f43d9c3829c4f53814e_MD5.jpg)

- **Archivo**: assets/screens/loading.scr    
- **Propósito**: Se muestra durante la carga del juego en el ZX Spectrum. Es la primera impresión del usuario, por lo que debe ser atractiva y representativa del tema del juego.
- **Especificaciones**:
	- Formato SCR, resolución de 256x192 píxeles, paleta de 15 colores (1 bit por píxel para brillo, con atributos de color de 8x8 píxeles).
	- Tamaño: 6912 bytes (6,75 KB).
- **Consideraciones**:  
    - Usa ZX Paintbrush para crear o editar la imagen. Puedes partir de ejemplos en la carpeta assets/screens.       
    - Optimiza para minimizar conflictos de color (color clash) debido a las limitaciones de atributos del ZX Spectrum.        

Resultado actual (1 iteración):

Ahora es cuando empieza el [Pixel Art Attack al mas puro estilo Errazkin](https://youtu.be/r_t6IBm8-Ac?si=bB0Ae1R50DPvP5eQ) XD

![Loading Screen Cursed Zapatilla 0001](PublicBrain/_resources/f5ae0ef26feaa587831f514988771420_MD5.jpeg)

---
### Menú (Pantalla Principal)

> OJO TEXTO SIN AFINAR

- **Archivo**: assets/screens/title.scr
- **Propósito**: Se muestra tras la carga, presentando las opciones de control al usuario antes de iniciar el juego. Incluye opciones como:
    - Teclado        
    - Kempston        
    - Sinclair        
    - Redefine (si está habilitado en la configuración).
- **Especificaciones**:
    - Formato SCR, resolución de 256x192 píxeles, paleta de 15 colores.
    - Tamaño: 6912 bytes (6,75 KB).
- **Consideraciones**:
- Se debe incluir el logo de ZX Game Maker, disponible en la carpeta de recursos o en la documentación.
    - Diseña un layout claro para mostrar las opciones de control, asegurándote de que el texto sea legible (fuentes monocromas o con alto contraste).
    - La pantalla debe ser estática y no animada para ahorrar memoria y ciclos de CPU.

### Ending

> OJO TEXTO SIN AFINAR

- **Archivo**: assets/screens/ending.scr
- **Propósito**: Se muestra cuando el jugador completa el juego, ofreciendo una conclusión visual satisfactoria.
- **Especificaciones**:
       - Formato SCR, resolución de 256x192 píxeles, paleta de 15 colores.
    - Tamaño: 6912 bytes (6,75 KB).
- **Consideraciones**:
    - Puede incluir mensajes de felicitación, créditos o un resumen del logro del jugador.
    - Usa ZX Paintbrush para diseñar una imagen que refleje el tema del juego y evite conflictos de color.
    - Al igual que la pantalla de carga, su impacto en la memoria es fijo y predecible.

### HUD

> OJO TEXTO SIN AFINAR

- **Archivo**: assets/screens/hud.scr
- **Propósito**: Se muestra en la parte inferior de la pantalla durante el juego para indicar información como vida, munición, llaves, ítems, marcador, combustible y mensajes.   
- **Especificaciones**:    
    - Formato SCR, resolución de 256x192 píxeles, pero solo se diseña la parte inferior (aproximadamente un tercio de la pantalla, ~64 píxeles de altura).
    - Tamaño: 6912 bytes (6,75 KB), aunque solo una porción se usa activamente.
- **Configuración de elementos**:
	- Usa el archivo assets/screens/hud.tmx en Tiled para posicionar los elementos del HUD en la capa de objetos. Cada elemento tiene un color e inicial distintiva:
        - **L** (Life): 3 caracteres.
        - **A** (Ammo): 3 caracteres.
        - **K** (Keys): 2 caracteres.
        - **S** (Score): 5 caracteres.
        - **I** (Items): 2 caracteres.
        - **M** (Messages): 2 líneas de 8 caracteres.
        - **F** (Fuel): 3 caracteres.
- **Consideraciones**:
- Diseña solo la parte inferior para ahorrar esfuerzo y optimizar el uso de memoria.
    - Asegúrate de que los elementos sean claros y no se solapen visualmente.
    - La edición en Tiled permite ajustar las posiciones sin modificar el código del juego.

## Pantallas Opcionales (Solo 128K)

> OJO TEXTO SIN AFINAR

### Intro
- **Archivo**: assets/screens/intro.scr
- **Propósito**: Se muestra después de seleccionar el método de control y antes de iniciar el juego. El usuario debe pulsar _Enter_ para continuar.   
- **Especificaciones**:    
    - Formato SCR, resolución de 256x192 píxeles, paleta de 15 colores.        
    - Tamaño: 6912 bytes (6,75 KB).        
    - Solo disponible en la versión 128K (128Kenabled).
- **Consideraciones**:   
    - Si el archivo no existe en assets/screens, el motor omite esta pantalla y el juego comienza directamente.        
    - Ideal para mostrar una breve narrativa o introducción al contexto del juego.            - Su uso incrementa el consumo de memoria, por lo que debe justificarse en juegos 128K.
       
### Game Over

> OJO TEXTO SIN AFINAR

- **Archivo**: assets/screens/gameover.scr    
- **Propósito**: Se muestra cuando el jugador pierde todas sus vidas, antes de volver al menú principal. El usuario debe pulsar _Enter_ para continuar.    
- **Especificaciones**:    
    - Formato SCR, resolución de 256x192 píxeles, paleta de 15 colores.        
    - Tamaño: 6912 bytes (6,75 KB).        
    - Solo disponible en la versión 128K (128Kenabled).        
- **Consideraciones**:    
    - Si el archivo no existe, el motor muestra un texto predeterminado de "GAME OVER" en el centro de la pantalla y espera a que se pulse _Enter_.        
    - Diseña una imagen temática que refuerce la sensación de derrota, pero manténla simple para no sobrecargar la memoria.        
    - Al igual que la pantalla de introducción, su uso está limitado a configuraciones 128K.

## Referencias Bibliográficas

* Mis pruebas de campo ⚫①
* [Documentación oficial del proyecto 🌐🟡③](https://gm.retrojuegos.org/index.html)
* [Repositorio de Github de ZX Game Maker 🌐🟡③](https://github.com/rtorralba/zx-game-maker) .
* [Página de Itch.io del proyecto 🌐🟡③](https://juntelart.itch.io/zx-game-maker)

![[Plantilla - 1MT#One More Thing]]