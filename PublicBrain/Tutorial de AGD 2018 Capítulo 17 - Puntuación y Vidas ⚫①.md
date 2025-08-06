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
created: 2025-07-26T05:42:37.582Z
modified: 2025-08-06T22:54:13.481Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 17 - Puntuación y Vidas ⚫①

![Game Over en JBA](PublicBrain/_resources/de50fdb8c54a66c181e9c8473d6eaddc_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 16 - Nuestro primer enemigo. ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capítulo 18 - Optimiza tu código ⚫①|Siguiente >>]]

En el anterior capítulo creamos nuestro primer enemigo, es hora de gestionar el proceso cuando un enemigo, o el escenario "nos mata", no es dificil, pero hay que pensarlo con cuidado.

## Gestionando la Puntuación

Empecemos por lo menos controvertido, "los puntos", en realidad con AGD es extremadamente sencillo, contamos con dos instrucciones básicas: SCORE y SHOWSCORE.

SCORE nos permite añadir una determinada cantidad de puntos a la puntuación general, se suele utilizar por ejemplo en código que gestiona la muerte de un enemigo, o la adquisición de un objeto, depende íntegramente del creador del juego decidir cuales son las acciones que se recompensan con una determinada cantidad de puntos en su juego.

SHOWSCORE sirve para mostrar la puntuación total actual en la posición del cursor (que podemos ajustar apropiadamente antes de ejecutar esta instrucción). Dependiendo del juego, se puede refrescar la puntuación una sola vez por ciclo en algún punto del bucle principal, o justo tras sumar puntos, el método concreto nuevamente depende de tu juego y de donde puedes tu tener cuellos de botella, o no.

Hay una tercera instrucción, BIGSCORE, que a priori parece pensada para mostrar, por ejemplo, la puntuación al final del juego, pero si se gestiona correctamente podría usarse perfectamente para mostrar la puntuación en un marcador más grande de lo habitual, la imaginación es el límite.

Desconozco, en el momento de escribir estas líneas, que límite superior tiene la puntuación, de existir esa información pública, no he logrado localizarla. (Si tu conoces el dato, por favor aporta esta información en los comentarios). La hipótesis con la que yo trabajo es que esta puntuacion máxima es 999.999, dado que al imprimir con SHOSCORE, aparecen seis digitos (como en el ejemplo de la imagen de cabecera).
## Gestionando las vidas

Es un tema a gestionar con cuidado, pero en realidad se basa en herramientas sencillas, disponemos de la variable global LIVES que contiene el número de vidas actual y permite trabajar operaciones y condicionales con ella, la instrucción DISPLAY que permite mostrar el valor de esta variable donde sea necesario, y el evento «Kill Player» que es donde escribiremos el código para restar las vidas, y mostrar el número de estas tras una muerte.

Esencialmente todos los lugares (colisiones o caidas principalmente) donde nuestro personaje deba perder una vida contendrán la instrucción KILL, esto provoca la ejecución del evento Kill Player. Es este evento el que se encarga de:

1. Restar una vida al jugador
2. Si las vidas han llegado a cero entonces AGD ejecutara automáticamente el evento «Lost Game», en el que se finaliza el juego y se vuelve a menú principal.
3. Mostrar cualesquiera efectos , o actualizaciones (como el contador de vidas) que proceda.
4. Bien esperar un tiempo o bien una tecla y terminar, AGD volverá a cargar la pantalla en la que has muerto con el protagonista en la posicion inicial definida para la pantalla actual (lo explico más abajo).
5. 
Poco más, el que quede más o menos bonito, con más o menos sonido, ya dende de nuestra imaginación, ¡como os digo siempre!
### El evento «Lost Game»

Es el bloque de código que se ejecuta al perder todas las vidas y justo después de el se regresa al menú principal del juego, es el evento en que se efectúan los efectos adecuados al final del juego, se muestran carteles de Game Over y/o la puntuación final, o incluso se puede ejecutar algún tipo de sonido (el sonido lo explicare en capítulos muy avanzados del tutorial, pues quiero cubrir los métodos nativos de AGD y también la inclusión de música AY)

Tras este evento, el protagonista aparecerá en la "posición por defecto para el sprite de tipo 0" de cada pantalla, que hemos de definir específicamente para esto, hemos de acceder a «Sprite Positions» y, para cada pantalla del juego en que se pueda morir, definir una posición por defecto para nuestro protagonista. En ese punto aparecemos si perdemos una vida.
### Vidas Extra

El decidir en qué condiciones se puede premiar al jugador con una vida extra depende de multitud de factores: la dificultad, el tipo de juego, el diseño del mapeado, etc. En esencia tú, como creador debes decidir como debe ser.

Se puede adjudicar una vida extra al llegar a determinada puntuación, o al lograr hacerse con un objeto determinado (los objetos los trataré en capítulos específicos más adelante), cuando la condición que hemos decidido como adecuada para obtener una vida extra se cumple, tan solo tendremos que ejecutar ADD sobre la variable LIVES (y actualizar el contador de vidas en pantalla para reflejar el cambio). En el fondo es sencillo, solo requiere planificación.

Y por supuesto, un buen testeo para no hacer el juego demasiado fácil, o imposible, es de vital importancia, recordemos que estamos en el siglo 21 con una amplia oferta y si nos empeñamos en dificultar la vida al jugador en demasía, este no jugará a nuestro juego.

Aprovechando que hemos comentado parte del ciclo de vida del juego, en futuros capítulos lo trataré a nivel global, de forma que ya prosigamos con una visión de conjunto de como «funciona» el juego, lo que nos facilitará decidir donde situar cada bloque de código en función de su objetivo, pero eso, como digo, en próximas entregas :)

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**. 

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si tienes muchos puntos, presentate en enfermería en la página 1]]
* [[Tutorial de AGD 2018 Capítulo 17 - Puntuación y Vidas ⚫①|Si no te da la vida, espera que aparezca el mensaje Game Over, y pasa a la página 17]]
* [[Tutorial de AGD 2018 Capítulo 18 - Optimiza tu código ⚫①|Si has logrado que te de la vida para más, pasa a la página 18 en cuanto la puntuación te lo permita.]]

![[Plantilla - 1MT#One More Thing]]