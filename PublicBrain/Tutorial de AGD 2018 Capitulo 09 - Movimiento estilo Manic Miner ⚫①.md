---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-06-25T23:02:39.435Z
modified: 2025-06-26T08:28:03.318Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
---
# Tutorial de AGD 2018 Capitulo 09 - Movimiento estilo Manic Miner ⚫①

![La cabeza de Manic Miner con pixeles gordos](PublicBrain/_resources/adf42fadbabbecc0aca89de02719db4d_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 08 - Mover a nuestro protagonista por la pantalla ⚫①|<< Anterior ]] | Siguiente >>

En el último capítulo pudimos, por primera vez, [[Tutorial de AGD 2018 Capitulo 08 - Mover a nuestro protagonista por la pantalla ⚫①|mover nuestro personaje por la pantalla usando el teclado]]. 

En esta ocasión explicaré el código de la plantilla por defecto de tipo "Manic Miner" y que nos servirá de base para nuestro juego.

Antes de nada, y para facilitar el manejo del editor de código, veamos las teclas de control del editor de código de AGD, tendrás que ver en tu emulador y sistema operativo, cual es la correspondencia entre las teclas "especiales" de ZX Spectrum y las de tu máquina real.

```pre
- SYM-Y Cortar Línea
- SYM-U Pegar Linea
- SYM-Q Inicio
- SYM-E Fin
- CAPS-2 Activar Mayúsculas
- CAPS-3 Borrar hacia delante
- CAPS-4 Cambia entre Insertar y Sobreescribir
- SYM-CAPS Activa/Desactiva Modo Extendido </pre>
```
## ¿Manic Miner?

Cabe la posibilidad de que no hayas conocido el juego al que nos referimos, un clásico de los 80, básicamente el movimiento consiste en tres teclas, izquierda, derecha y salto. En el siguiente video podeis ver ese estilo en acción:

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/FCvgGGe71X4?si=tTZJmf-t8ENA8l7-" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

## ¡Al lio!

Pongo en primer lugar el código completo, para a continuación ir desgranándolo, ¡vamos a ello!

```BASIC
IF KEY 0
	IF Y > 167
		SCREENRIGHT
		LET Y = 6
		EXIT
	ELSE
		IF CANGORIGHT
			LET IMAGE = 0
			ANIMATE
			SPRITERIGHT
		ENDIF
	ENDIF
ENDIF
IF KEY 1
	IF Y < 8
		SCREENLEFT
		LET Y = 168
		EXIT
	ELSE
		IF CANGOLEFT
		LET IMAGE = 0
		ANIMATE
		SPRITELET
	ENDIF
ENDIF
IF KEY 3
	JUMP
ENDIF
FALL
IF DEADLY
	KILL
ENDIF
```

Lo primero que hemos de observar es la estructura del código, básicamente hay cuatro partes, delimitadas más o menos por cada IF, a saber: movimiento a la derecha, movimiento a la izquierda, salto y caída.

```BASIC
IF KEY DERECHA
	MOVER DERECHA
ENDIF
IF KEY IZQUIERDA
	MOVER IZQUIERDA
ENDIF
IF KEY SALTO
	SALTAR
ENDIF
GESTIONAR CAIDA
SI CAYO DE DEMASIADO ALTO
	GESTIONAR MUERTE
ENDIF
```

## Movimiento Derecha

```BASIC
IF KEY 0
	IF Y > 167
		SCREENRIGHT
		LET Y = 6
		EXIT
	ELSE
		IF CANGORIGHT
			LET IMAGE = 0
			ANIMATE
			SPRITERIGHT
		ENDIF
	ENDIF
ENDIF
...
```

El primer bloque "IF" gestiona el movimiento del muñeco cuando pulsamos el KEY 0 que corresponde con la tecla asignada a "Derecha", se ejecuta el código que hay dentro.

Este código se divide en dos partes, la primera comprueba si estamos en el borde derecho de la pantalla para cambiar a la que corresponde en el mapa (de momento sólo tenemos una) , la otra, en caso de que no estemos en ese borde, gestiona el movimiento natural de nuestro protagonista.

```BASIC
...
IF Y > 167
	SCREENRIGHT
	LET Y = 6
	EXIT
ELSE
...
```

En primer lugar, indicar que Y es la variable que representa la posición horizontal del sprite de nuestro protagonista, dentro de la pantalla, el número exacto dependerá de las dimensiones que hayamos asignado a la pantalla de juego. Léase el 167 como "límite derecho de la pantalla actual" y el 6 como "límite izquierdo de la pantalla actual".

La primera instrucción SCREENRIGHT, muestra la pantalla "a la derecha" de la actual según el mapa, en caso de no haber ninguna, muestra la misma de nuevo.

A continuación cambia la coordenada Y, de forma que "desaparecemos" por a derecha de una pantalla y "aparecemos" en la parte izquierda de la correspondiente.

Por último, salimos del bloque de código, pues ya hemos respondido a la pulsación de tecla. Tomemos en cuenta que este bloque de código se ejecuta continuamente por lo que prima la norma "una tarea cada vez".

Veamos ahora el "ELSE", que corresponde con la gestión del movimiento "normal" del muñeco:

```BASIC
...
ELSE
	IF CANGORIGHT
		LET IMAGE = 0
		ANIMATE
		SPRITERIGHT
	ENDIF
ENDIF
...
```

El funcionamiento es muy sencillo, si "CANGORIGHT", entonces, se asigna el sprite 0 como gráfico del muñeco, se ejecuta el ciclo de animación y se mueve el sprite hacia la derecha. Es muy muy sencillo, pero quiero comentar un par de cosas:

* En primer lugar, CANGORIGHT hace referencia a la comprobación de si los bloques dibujados en pantalla permiten "cruzar" al personaje, he estado esperando hasta este punto para contar esto. Sirva decir que cada bloque puede o no dejar pasar (ser suelo, pared , etc) en función de la configuración y que esto hará que nuestro muñeco pueda o no pasar por determinada zona. Podéis jugar con eso en el editor de bloques y ver que pasa, aunque dedicaré un capítulo a esto próximamente.
* En segundo lugar el "LET IMAGE = 0", asigna un sprite o secuencia frames al muñeco, podemos tener varias de estas secuencias y asignarlas en determinados momentos como por ejemplo, una para cuando estamos quietos, otra para movernos a la derecha, otra para movernos a la izquierda y otra para el salto.

Mediante esta asignación iremos cambiando la animación por la que toca en cada momento. Como "deberes", haced que vuestro muñeco tenga una animación estando quieto, otra para moverse en cada dirección (izquierda o derecha) y otra diferente para el salto. Es un gran ejercicio que os hará encontrar y resolver problemas, algo muy necesario para crear un juego.

## Movimiento Izquierda

```BASIC
...
IF KEY 1
	IF Y < 8
		SCREENLEFT
		LET Y = 168
		EXIT
	ELSE
		IF CANGOLEFT
		LET IMAGE = 0
		ANIMATE
		SPRITELET
	ENDIF
ENDIF
...
```

El movimiento a la izquierda es literalmente la [imagen especular 🌐🟡③](https://es.wikipedia.org/wiki/Imagen_especular) del de mover a derecha, por lo que me remito a lo ya explicado.

## Salto

```BASIC
...
IF KEY 3
	JUMP
ENDIF
FALL
IF DEADLY
	KILL
ENDIF
```

Por último, el salto, en su versión más básica, simplemente comprobamos que se ha pulsado la tecla correspondiente al salto, y ejecutamos la rutina que lo gestiona.

Posteriormente ejecutamos FALL que gestiona la caída en caso de que el salto termine "en el aire". Esta rutina, en caso de que caigamos desde demasiado alto, activará el FLAG "DEADLY".

Finalmente, si el proceso acaba con "DEADLY" en "verdadero", se ejecuta "KILL" que gestiona el proceso de muerte lanzando el evento correspondiente (en el que a su vez estará el código que resta las vidas y demás).

Y esto sería todo por hoy, se pueden hacer más cosas, jugad con el código a ver que cosas se os ocurren, tambien podeis crear pantallas a izquierda y derecha de la que tenéis, situarlas en el mapa y ver como cambiamos de una a otra al acercarnos al borde.

En próximos capítulos crearé una traducción de la "Referencia de Lenguaje" de AGD, y en capítulos posteriores hablaré de los tipos de bloque, del salto, el proceso de "muerte", y como suele decirse ¡y mucho más! xD

Como decimos siempre practicad, practicad y practicad. ¡Nos vemos en la siguiente entrega!

## ¿Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si hs aterrizado aquí directamente desde Ventormenta sin encargarte de Hogger, pasa a la página 1]]
* [[Tutorial de AGD 2018 Capitulo 09 - Movimiento estilo Manic Miner ⚫①|Si has ido y vuelto de Uldum cuando era todo campo, regocíjate hermano, que no es nada facil, desde la página 9]]
* Si no has podido librarte de Hogger y debes huir para conservar la vida, ve al instructor de portales y abre uno al futuro pasado de Terminator.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

![[Plantilla - 1MT#One More Thing]]