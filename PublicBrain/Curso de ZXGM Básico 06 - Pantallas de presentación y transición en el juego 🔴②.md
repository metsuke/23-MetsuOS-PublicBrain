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
modified: 2025-09-16T07:29:27.404Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 9
nav_primary: []
nav_secondary: []
tags: []
---
# Curso de ZXGM Básico 06 - Pantallas de presentación y transición en el juego 🔴②


![Lo que puede hacer MOS Game Maker Pro con una imagen](_resources/3b19842721da123761bcb57d9b51222a_MD5.jpeg)

* [[Curso de ZX Game Maker ⚫①]]
* [[Pixel Art Attack - Cursed Zapatilla - ZX Spectrum ⚫①]]
* [[Curso de ZXGM Básico 05 - Calibrando funcionalidad y memoria para nuestro juego 🔴②|<< Anterior]] | [[Curso de ZXGM Básico 07 - Creando nuestros Tiles 🟡③|Siguiente >>]]

> Este es un "Live Post" ya que nos vamos a tomar nuestro tiempo para hacer las pantallas con mimo, y así dar tiempo para la salida de la siguiente - espectacular - versión del engine, y que trae novedades que me interesa incorporar al juego.

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
    - Usa Retro-X para crear o editar la imagen. Puedes partir de ejemplos en la carpeta assets/screens.       
    - Optimiza para minimizar conflictos de color (color clash) debido a las limitaciones de atributos del ZX Spectrum.
    - A Partir de ahí trabajar con ZX-Paintbrush iterando sobre la imagen (puedes ver los pasos intermedios en [[Pixel Art Attack - Cursed Zapatilla - ZX Spectrum ⚫①]])

### Estado actual (Iteración 002):

Inicio de la automatización de la parte del proceso previa al trabajo artístico fino con MetsuOS Game Maker Tools.

Ahora es cuando empieza el [Pixel Art Attack al mas puro estilo Errazkin](https://youtu.be/r_t6IBm8-Ac?si=bB0Ae1R50DPvP5eQ) XD

![El punto al que he llegado con MetsuOS Game Maker Tools](PublicBrain/_resources/f1139e8c8ab76b7f55c6cc2f25dd559e_MD5.jpeg)

---
### Menú (Pantalla Principal)

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
    - Diseña un layout claro para mostrar las opciones de control, asegurándote de que el texto sea legible (fuentes monocromas y/o con alto contraste).
### Ending

- **Archivo**: assets/screens/ending.scr
- **Propósito**: Se muestra cuando el jugador completa el juego, ofreciendo una conclusión visual satisfactoria.
- **Especificaciones**:
       - Formato SCR, resolución de 256x192 píxeles, paleta de 15 colores.
    - Tamaño: 6912 bytes (6,75 KB).
- **Consideraciones**:
    - Puede incluir mensajes de felicitación, créditos o un resumen del logro del jugador.

### HUD

- **Archivo**: assets/screens/hud.scr
- **Propósito**: Se muestra en la parte inferior (el tercio inferior) de la pantalla durante el juego para indicar información como vida, munición, llaves, ítems, marcador, combustible y mensajes.   
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
### Estado actual (Iteración 004):

El proceso ha sido laborioso, y de aqui surge la necesidad de crear un modulo en mosGameMaker para definir elementos por separado y que todo se "monte solo", porque me lleva demasiado tiempo iterar. De momento he aqui el resultado y su aspectro ingame (recuerden que estamos trabajando con la demo del motor, transformandola en nuestro juego).

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```

![El HUD en Affinity Photo](PublicBrain/_resources/f0f7265d0f8dcee144cc88c76d8d34ea_MD5.jpeg)

 --- column-end ---

![El HUD Ingame](PublicBrain/_resources/f46057c80a427d173e986ba6750c5420_MD5.jpeg)
 --- column-end ---
--- multi-column-end

## Pantallas Opcionales (Solo 128K)

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