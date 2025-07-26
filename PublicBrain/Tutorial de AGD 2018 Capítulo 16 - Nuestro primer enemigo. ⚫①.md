---
iaStatus: 8
iaStatus_Model: Raúl Carrillo Garrido aka metsuke
iaStatus_Generado: "H"
iaStatus_Supervisado: "-"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-07-19T18:39:16.802Z
modified: 2025-07-26T05:44:06.040Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 16 - Nuestro primer enemigo. ⚫①

![Nuestro primer enemigo](PublicBrain/_resources/8fbc62c511b1fbf3b2b765372e9223ec_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 15 - El salto y sus posibilidades narrativas  ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capítulo 17 - Puntuación y Vidas ⚫①|Siguiente >>]]

Mucho hemos caminado desde que [[Tutorial de AGD 2018 Capitulo 03 - Nuestra primera pantalla  ⚫①|creamos nuestra primera pantalla]], [[Tutorial de AGD 2018 Capitulo 05 - Animando sprites ⚫①|nuestra primera animación]] o [[Tutorial de AGD 2018 Capitulo 08 - Mover a nuestro protagonista por la pantalla ⚫①|pusimos a nuestro prota en movimiento]]. Hoy vamos a comenzar a dar vida a nuestro primer enemigo.

Lo primero que hemos de tener en cuenta es que un enemigo, en realidad, no es mas que un sprite, con tipo distinto al cero, con sus animaciones como cualquier otro y que seguirá las normas establecidas en el bloque de evento del tipo que le corresponda.

No hay misterio, en esencia crearemos un sprite, lo animaremos, decidiremos el tipo y crearemos el código correspondiente en el evento. Si no has [[Tutorial de AGD 2018 Capitulo 04 - Los Sprites aka creando el Muñequito y los Bichos ⚫①|creado ya el gráfico y animaciones]] de tu enemigo, hazte uno (o copia el mio, que puedes observar en la imagen que preside este artículo) y vuelve, ¡te esperamos antes de continuar!.

## Situar el Enemigo en Pantalla

Al igual que nuestro protagonista, hemos de situar la posición inicial de nuestro enemigo en la pantalla, a partir de esa posición el enemigo actuará siguiendo el código que tenga asignado según el tipo (lo que quiere decir que podemos hacer que un mismo sprite animado actúa de varias formas segun el tipo que le asignemos en la pantalla de Sprite Positions, a la que se acceder mediante a tecla N. Aparecemos en una pantalla como la siguiente:

  ![Pantalla de configuración de posiciones iniciales de spritesde AGD](PublicBrain/_resources/e3cd451f53851ea1935c7888c070339f_MD5.jpg)

Antes de nada, las referencia de comandos de teclado:

```pre
* N = Pantalla siguiente
* P = Pantalla Anterior
* Q = Seleccionar sprite siguiente
* I = Cambiar la imagen del sprite
* T = Cambiar el tipo del sprite
* D = Eliminar el sprite seleccionado de la pantalla.
* X = Añadir nuevo sprite a la pantalla.
```

Para crear nuestro primer enemigo, añadiremos un nuevo sprite con X, usando los cursores para situarlo en la posición deseada, con I elegiremos la imagen del sprite que hemos diseñado y con T seleccionaremos tipo 1 (hay 9 incluyendo el del jugador, pero usaremos este) que es el que vamos a usar en este ejemplo. ¡Listo! ya tenemos el sprite de nuestro enemigo, que podremos ver si ejecutamos el juego ... pero claro, no se mueve, veamos como darle vida.

## Códgo en el Evento "Sprite Type 1"

Vamos al menú principal, entramos en Eventos y seleccionamos el Evento "Sprite Type 1", saldrá nuestra vieja conocida lista de plantillas, seleccionaremos "Patrolling Enemy (U/D)" y pulsaremos space, esto cargará en el evento el código de un enemigo que patrulla su área rebotando arriba y abajo. Concretamente el siguiente:

```BASIC
IF PARAMA = 0
  IF CANGOUP
	SPRITEUP
  ENDIF
ELSE
  LET PARAMA = 1
ELSE
  IF CANGODOWN
	SPRITEDOWN
  ELSE
	LET PARAMA = 0
  ENDIF
ENDIF
ANIMATE
IF COLLISION 0
  KILL
ENDIF
```

Este código es bastante sencillo y podemos observar que muchos de los conceptos que utiliza ya los conocemos, pues los estudiamos en el [[Tutorial de AGD 2018 Capitulo 09 - Movimiento estilo Manic Miner ⚫①|código para el jugador]].

Una diferencia primordial es que el código de este enemigo no usa para nada las pulsaciones de tecla realizadas por el jugador, en cambio usa PARAMA (variable disponible para cada sprite) para indicar si el sprite sube (PARAMA = 0) o baja (PARAMA = 1).

En esencia, evalúa la dirección actual del movimiento, y según este comprueba si puede CANGOUP / CANGODOWN, si puede, movemos el sprite si no se puede, se asigna PARAMA para cambiar de dirección. Vemos, por tanto, que [[Tutorial de AGD 2018 Capitulo 11 - Tipos de Tiles ⚫①|los tipos de bloque afectan a todos los sprites]], no solo al protagonista.

Tras la comprobación de movimiento, se ejecuta un ANIMATE para que la animación avance un frame.

Por último , se comprueba COLLISSION 0 que significa "SI he colisionado con un sprite de tipo 0" (el jugador) entonces KILL (es decir quita una vida al jugador). 

Ahora si, si ejecutamos el juego veremos que nuestro enemigo se mueve y si nos toca, moriremos (no nosotros, el muñequito en pantalla xD).

Y poco más, esto es lo básico de un enemigo, en el próximo capítulo trataré la gestión de KILL y la puntuación básica, como veis poco a poco esto comienza a tomar forma, eso si, no dudéis en trastear con las opciones, las plantillas de enemigo y demás opciones de AGD, este tutorial es una guía que apoya vuestro trabajo de investigación, ensayo y error, pero que en ningún caso puede sustituir este esfuerzo por vuestra parte.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no sabes quien es amigo o enemigo, busca refugio en la página 1]]
* [[Tutorial de AGD 2018 Capítulo 15 - El salto y sus posibilidades narrativas  ⚫①|Si cada vez que insertas un enemigo saltan los promos, ve a comprobar el diferencial en la página 15]]
* [[Tutorial de AGD 2018 Capítulo 16 - Nuestro primer enemigo. ⚫①|Si crees que ha llegado el momento pero no sabes cuando, pasa a la página 16]]
* [[Tutorial de AGD 2018 Capítulo 17 - Puntuación y Vidas ⚫①|Si ya lo tienes todo claro, espera que aparezca la salida, y pasa a la página 17]]

![[Plantilla - 1MT#One More Thing]]