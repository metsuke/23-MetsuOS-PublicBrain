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
created: 2025-07-30T04:40:22.150Z
modified: 2025-08-01T04:01:00.454Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 19 - Ciclo de vida ⚫①

![Ciclo de vida](PublicBrain/_resources/12ff93fbb99bffab5cfc48cfc9e0fc87_MD5.jpg)

 * [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 18 - Optimiza tu código ⚫①|<< Anterio]] | [[Tutorial de AGD 2018 Capítulo 20 - Creando Objetos ⚫①|Siguiente >>]]

¿Ciclo de vida? si, con ello me refiero a los eventos, en que orden y cuando se ejecutan. Es importante reseñar que en AGD no hay concurrencia, es absolutamente lineal, por lo que solo se puede ejecutar una cosa al tiempo.

Cada uno de los eventos de que dispone AGD se lanza en un momento diferente:

## Intro / menu

Este evento es el primero que se ejecuta al iniciar la ejecución del programa, se encarga de gestionar el menú y pantalla de presentación.

 Al iniciar el juego desde el menu se ejecuta \"Game initialisarion\"

## Game initialisarion

En este evento se realizan las configuraciones iniciales de la partida, se dispone el número de vidas, y, en general, todo lo que deba realizarse al comienzo de la partida.

En este punto se carga la primera pantalla, se invocan a los sprites, y por cada uno de ellos se ejecuta \"Initialize sprite\"

## Initialize sprite

Este evento se ejecuta al comienzo de la primera pantalla del juego, cada vez que cambiamos de pantalla y se crea un sprite y en general en cualquier punto en que aparezca uno nuevo (como por ejemplo un disparo).

Sirve únicamente para inicializar valores de los mismos, sin más complicación. En el caso del inicio de la partida, a continuación se salta a \"Main loop 1\"

## Main loop 1

El comienzo del ciclo de juego principal que se repite una y otra vez empezando por este evento. Aquí se debe incluir lo que se necesite ejecutar antes de comprobar y mover los sprites incluyendo al protagonista.

Tras este evento, se ejecuta el control del jugador \"Player control (type 0)\"

## Player control (type 0)

En este evento se gestiona el control del jugador, desde el movimiento a la recogida de objetos e incluso los disparos.

En este evento pueden suceder varias cosas:

* En caso de que caigamos desde demasiado alto se ejecuta **Fell-too-far**
* Si por cualquier motivo el personaje principal pierde una vida, saltamos a **Kill player**
* Aunque puede ejecutarse en cualquiera de los loops por ejemplo, en mi caso con JBA compruebo aquí la condición de victoria, si se cumple, salto a **Completed game**
* En caso de un flujo sin novedad se continúa con **Sprite type 1 .. 8**

## Sprite type 1 .. 8

En estos eventos se procesan en secuencia los diferentes tipos de sprite (enemigos, balas, etc), en caso necesario, se ejecuta un **Kill player**, en caso contrario salta a **Main loop 2**

## Main loop 2

Tras el procesado de todos los sprites se ejecuta la segunda parte del loop principal, y si no sucede nada reseñable, se vuelve a **Main Loop 1**.

## Fell too far

Cuando AGD detecta que el jugador ha caído desde demasiada altura, se activa este evento, en el que se puede reaccionar ante esta situación, en caso de que se considere oportuno, se puede ejecutar la pérdida de una vida, ejecutándose **Kill player**.

## Kill player

En este evento se gestiona la pérdida de una vida por parte del jugador, si se han perdido todas las vidas se salta automáticamente a **Lost game**, en caso contrario se salta a **Restart screen** y se continua la partida.

## Restart screen

Este evento nos permite gestionar las acciones apropiadas al reiniciar una pantalla tras la pérdida de una vida, y acto seguido se vuelve a **Main loop 1**
## Lost game

Este evento permite gestionar lo que ocurre al perder todas las vidas, mensaje de game over, sonidos de fin de juego , etc. 

Tras su ejecución se lanza **Intro / menu**

## Completed game

Si en algun punto se cumple la condicion de victoria, se lanza este evento que nos permite definir que va a ocurrir cuando el jugador logre pasarse nuestro juego, podemos hacer multitud de cosas para recompensar a ese jugador que se ha esforzado al máximo.

Cuando se completa este evento, se lanza **Intro / menu**, cerrando el ciclo.

Un ciclo bastante sencillo sin duda, pero que por su sencillez sirve de ejemplo minimalista del proceso que lleva a cabo un videojuego mietras nosotrs disfrutamos de la partida. 

Aún no he decidido que voy a comentar en el próximo capítulo por lo que esta vez será sorpresa ¿quizá los objetos?¿el de textos? debo pensarlo.
## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**. 

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si tienes muchos optis pero pocos mizas, presentate en enfermería en la página 1]]
* [[Tutorial de AGD 2018 Capítulo 18 - Optimiza tu código ⚫①|Si crees que puedes mejorar aún más tu vida recursivamente, pasa a la página 18]]
* [[Tutorial de AGD 2018 Capítulo 19 - Ciclo de vida ⚫①|Si ya no puedes con tu vida, pero crees que es cosa de esperar el cambio de ciclo, pasa a la página 19]]
* [[Tutorial de AGD 2018 Capítulo 20 - Creando Objetos ⚫①|Si estás deseando salir del bucle, y seguir con tu vida, espera tu oportunidad, y pasa a la página 20]]

![[Plantilla - 1MT#One More Thing]]