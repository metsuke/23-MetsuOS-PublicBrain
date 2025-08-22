---
iaStatus: 8
iaStatus_Model: Raúl Carrillo Garrido aka metsuke
iaStatus_Generado: H
iaStatus_Supervisado: "-"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-08-20T15:38:17.242Z
modified: 2025-08-20T18:17:25.494Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoAGD001.mp4
---
# Tutorial de AGD 2018 Capítulo 32 - Información detallada sobre la estructura en memoria de AGD ⚫①

![Información detallada sobre la estructura en memoria de AGD](PublicBrain/_resources/41c8adbac8af58f4201152fec1347ad1_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 31 - Ejemplo básico jugando con tipos y animaciones ⚫①|<< Anterior]] |  Siguiente >>

Gracias a [Sergio thEpOpE  🌐🟡③](https://www.youtube.com/c/thEpOpESergio), tenemos disponible un increible documento, que convierto a html a continuación, adicionalmente, puedes consultar este [artículo que nos muestra como trabajar con ASM desde AGD](https://web.archive.org/web/20190326191446/https://www.funspot.it/agd-asm-calls).

## AGD Technical Info, by Sergio-thEpOpE

<code>Creative Commons - CC by (Trascrito en 22 09 27)</code>

### Versión 4.7 y 4.8

* 7d05 b- Sistema de input (0 Keyboard,1 Kempston,2 Sinclair)
* 7D06 b- Estado actual del teclado/joystick (teclas pulsadas)
* 7d07 b- Frame seleccionado en el editor
* 7D08 b- top del area de juego
* 7D09 b- left del area de juego
* 7D0A b- alto del area de juego
* 7D0B b- ancho del area de juego
* 7D0C b- top px : estos 4 valores son las coordenadas de los pixels del area de juego
* 7D0D b- left px
* 7D0E b- abajo px
* 7D0F b- derecha px
* 7d10 b- Numero de sprites
* 7d11 b- Numero de bloques
* 7d12 b- Numero de pantallas
* 7d13 b- Numero total de frames que hay en el juego (lo usa el compilador para calcular rotaciones)
* 7d14 b- Numero de mensajes
* 7d15 b- Numero de sonidos
* 7d16 b- Elemento seleccionado (se usa en el editor, para avanzar por los sonidos, etc...)
* 7d17 w- Shadow del puntero de la tabla de sonidos? - Es el que usa el editor
* 7d19 b- Elemento seleccionado de los textos
* ...
* 7d1a b- Numero de objetos
* 7D1B b- SCREEN
* 7D1C b- LIVES
* 7D1D b- A (variables)
* 7D1E b- B
* 7D1F b- C
* 7D20 b- D
* 7D21 b- E
* 7D22 b- F
* 7D23 b- G
* 7D24 b- H
* 7D25 b- I
* 7D26 b- J
* 7D27 b- K
* 7D28 b- L
* 7D29 b- M
* 7D2A b- N
* 7D2B b- O
* 7D2C b- P
* 7D2D b- Q
* 7D2E b- R
* 7D2F b- S ;(en la versión 4.6 no existen las variables S y T, por lo que a partir de LINE están en el mismo orden, pero 2 bytes antes)
* 7D30 b- T

```pre
en la versión 4.6 no existen las variables S y T, por lo que a partir de LINE están en el mismo orden, pero 2 bytes antes
```
  
* 7D31 b- LINE
* 7D32 b- COLUMN
* 7D33 b- CLOCK ;esta variable la usa internamente para sincronizar ciclos del juego
* 7D34 b- RND
* 7D35 b- OBJ
* 7D36 b- OPT
* 7D37 b- nextlevel state (7D = nextlevel on)
* 7D38 b- restart state (1 = restart todos los sprites, 2 = restart pero manteniendo al jugador)
* 7D39 b- kill state (7D = kill on)
* 7D3A b- endgame state (7D = endgame on)
* 7D3B w- SpriteFramesTable (frame Inicial, numero de frames)
* 7D3D w- Sprite Images
* 7D3F w- Blocks ptr (bits de cada bloque)
* 7d41 w- Blocks Attr (atributo de color de cada uno de los bloques)
* 7d43 w- Blocks Type (tipo de bloque: empty, ladder, deadly, etc...)
* 7D45 w- ScreenPtr
* 7D47 w- EnemigosPtr (es la tabla de sprites situados en cada pantalla)
* 7D49 w- SoundPtr
* 7D4b w- Tabla de mensajes (cada mensaje termina con el último carácter poniendo el bit7 a 1)
* 7D4D w- ObjectsPtr
* 7D4F w- SourceCodePtr
* 7D51 w- CompiledPtr
* 7D53 w- FreespacePtr
* ...
* 8315 b- height of sprites (AGDx, 4.8)
* ...
* 83BF w- Si es $0555 la ordenación de sprites está OFF; de otro modo está on (v4.8/)
* ...
* 86BD w- SEED de Random , al inicio del juego se inicializa con la variable FRAMES del Basic. (86BC en 4.8, 8692 en 4.6)
* 86BF b[6]- '000000' <- el score en formato string (8695 en 4.6)
* 8D05 b - Collision Distance
* 8D07 b - (collision_distance*2)+1
* ...
* 8D0C b - Collision Distance
* 8D0E b - (coolision_distance*2)+1

### ULA Palette: 64 bytes

* v4.6 - $7fc0 b(64) - 
* v4.7 y 4.8 - $7fdf b(64) - 
  
### Jump Table:

La tabla de salto termina con 99

* v4.6 - $8d79
* v4.7 - $8d8e
* v4.8 - $8d95

### Mapa

* v4.6 
	* 8fd8-903a: mapa
	* 903b b- Índice del mapa de inicio
* v4.7
	* 8fec-904e : mapa
	* 904f b- Índice del mapa de inicio
* v4.8
	* 8ff1-9053 : mapa
	* 9054 b- Índice del mapa de inicio
	
### Teclado

La lectura de las teclas en el momento de redefinir el teclado se hace con la rutina de rom $028E, cada tecla devuelve un scancode, que se sitúa en una tabla interna que comienza en $8A0B. Mientras se redefine se hace un chequeo de que no haya teclas repetidas.

### Rutina de Compilación

La rutina situada en $63E2 compila todo el SourceCode, hacia CompiledPtr, y actualiza todos los punteros del motor hacia determinados eventos. Cada vez que con ENTER se sale del selector de eventos se invoca a esta rutina. Se da por hecho el SourceCode es un bytecoded generado sin error, y que por tanto el código generado será coherente.

### Música AY

Se llama constantemente a 849A, para reproducir los sonidos que están en "cola" de reproducción por AY.

84BB - Buffer de registros para AY

Tiene hasta 3 sonidos en cada canal. Cuando uno se termina, lo pone a FF, y cuando ocurre así, llama a la función que pone el mezclador de ese canal a 0.

<p>Esto último hay que quitarlo para la musica ingame.</p>

v. 4.7: 8491 : Rutina que silencia todo, llama secuencialmente a los silenciadores de cada canal.

```asm
CALL $853C               ; 8491 Silencia el canal A, anularlo con un ret en la entrada. POKE $853c, 201
CALL $8549               ; 8494 Silencia el canal B, ""
CALL $8556               ; 8497 Silencia el canal C, ""
CALL $8572               ; 849A <- carga valores del canal A, si está activo, si no silencia llamando a $853C
CALL $84D2               ; 849D <- carga valores del canal B, si está activo si no silencia llamando a $8549
CALL $84FD               ; 84A0 <- carga valores del canal C, si está activo si no silencia llamando a $8556
LD HL, $84BB             ; 84A3 <- buffer de registros AY
LD DE, $0E00             ; 84A6
LD C, $FD                ; 84A9
L_84AB: LD B, $FF                ; 84AB
OUT (C), E               ; 84AD <- selecciçon del registro
LD A, (HL)               ; 84AF
LD B, $BF                ; 84B0
OUT (C), A               ; 84B2 <- escritura del valor
INC E                    ; 84B4
INC HL                   ; 84B5
DEC D                    ; 84B6
JP NZ, L_84AB            ; 84B7
RET                      ; 84BA
```  


## Referencias Bibliográficas

- Documentación aportada por Sergio thEpOpE  🟡③.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no que se acabe esto, ve a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 32 - Información detallada sobre la estructura en memoria de AGD ⚫①|Si te da rabia que esto acabe, o, pasa a la página 32]]
* Si detectas algo nuevo, pasa rapidamente a la página 33

![[Plantilla - 1MT#One More Thing]]