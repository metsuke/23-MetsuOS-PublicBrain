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
created: 2025-07-16T06:54:21.872Z
modified: 2025-07-17T01:14:21.882Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 15 - El salto y sus posibilidades narrativas  ⚫①


![AGD El salto y sus posibilidades narrativas](PublicBrain/_resources/0a31dff3971ca900b9e63b48d6d41a02_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 14 - Conectando panallas entre si  ⚫①|<< Anterior]] | Siguiente >>

En el capítulo de hoy vamos a tratar un tema central en los juegos de plataformas realizados con AGD: el salto. Lejos de ser una cuestión menor, su poder narrativo hace de esta función una de las más relevantes.

## Configuración del Salto

Lo primero es lo primero, para entrar a la pantalla de configuración del salto , desde el menú principal, pulsamos la letra J. Aparecerá una pantalla similar a la siguiente:

![Pantalla de configuración de la tabla de salto de AGD](PublicBrain/_resources/358bfeb5cd4d7bd3fcda59edab5d0c15_MD5.jpg)

Esta pantalla muestra lo que se denomina "Tabla de Salto", basicamente es un a línea de tiempo (eje X) y altura (eje Y), si lo queremos ver de un modo menos técnico, imaginemos que es una representación del efecto de la gravedad sobre nuestro personaje, a lo largo del tiempo.

La configuración es sencilla, nos movemos a izquierda y derecha con los cursores, usando arriba y abajo, ajustaremos la altura del punto en que nos encontramos de la curva, pulsando intro, volvemos al menú principal.

La imagen es la tabla de salto de JBA, podemos ver la parte ascendente y como baja algo más rápido al descender hasta el suelo. Hay que tener en cuenta que AGD usa esta tabla tanto para el salto (del inicio hasta el punto más alto) como para la caída (desde el punto más alto hasta el final), de modo que la """gravedad""" del juego sea coherente.

Un detalle más, según el manual, el punto de cambio entre subida y bajada lo calcula el propio AGD, por lo que no has de preocuparte más que de que esta tabla de salto sea coherente con la narrativa de tu juego.

## Contando Historias

¿Narrativa del juego en ZX Spectrum? ¡<strong>CLARO</strong>! por muy arcade que sea tu juego, estás contando la historia de una persona, un saltamontes, una ardilla planeadora, un módulo de aterrizaje, un ent inquieto o un robot ancestral de la superficie de la luna, y debes adaptar tanto el movimiento como el salto y caída a tal efecto.

>*¡Cuidado!* Parece que AGD establece el punto en que empieza la caida cuando el siguiente item de la secuencia de la curva es más bajo que el anterior, y continua desde ahí, por lo que jugar a subir y bajar dentro de la curva trae resultados rarísimos. Seguro que se pueden lograr cosas chulas hackeando este comportamiento pero ten en cuenta esta cuestión.

### Una Persona

Este es el caso más sencillo, total, una persona salta, la gravedad hace su trabajo y va frenando hasta que empieza a caer de nuevo. El movimiento finaliza cuando vuelve a tocar el suelo.

La curva resultante es puramente parabólica, como la de JBA, podemos variar la inclinación y velocidad de caída acorde a la situación (por ejemplo podria ser muy picuda si se salta con pértiga o aplanada si es salto de longutud. 

### Un saltamontes

Este es un caso algo diferente, en principio el salto será más largo y menos alto pero también hay un aspecto diferencial, y es que el animal ha de acumlar potencia en las patas y luego liberarla de forma explosiva para saltar.

Por ello por ejemplo se podrian poner unas cuantas posiciones planas, para luego subir a media altura muy rápidamente y después usar el resto de posiciones para bajar delicadamente hasta el suelo en una curva descendente directa.

### Una ardilla planeadora

Este caso sería ligeramente diferente, hasta donde he visto en alguno de esos documentales de la 2 que nadie reconoce ver, hay ardillas que suben por el tronco de un árbol y son capaces de planear hasta la copa de otro, eso si, tomando impulso horizontalmente de modo que acaban siempre más abajo de lo que estanan antes de planar.

Bien, para implementar esto, a más de crear algún tipo de sistema de escaleras-tronco de árbol que nos permita "subir antes de saltar", hemos de articular la curva de un modo distinto, en este caso "saltar" significa más bien "proyectarnos hacia arriba y planear. Para ello el saltito inicial debe proyectarnos ligeramente hacia arriba, pero inmediatamente debemos iniciar una curva descendente cuasi plana hasta tres cuartas partes de la línea, momento en el cual caeríamos de golpe, emulando lo que ocurre si quedamos sin impulso suficiente.

Hay que tener cuidado con esta opción para no provocar efectos no deseados y tener en cuenta que las "caídas al vacío" serán inmediatamente movimientos en los que planeamos. Lógico por otra parte pues es el medio de movimiento del animal, eso si, cuidado con las animaciones, que deben ser acorde a la acción que estamos representando.

### Un módulo de aterrizaje

En este caso, a más de tener cuidado con la coherencia de las animaciones, hemos de cuadrar bien el timing del salto, tomemos por ejemplo un módulo de descenso en la luna, que se mueve por pequeños impulsos con los retrocohetes.

La primera cuestión a tomar en cuenta es que lógicamente se tratará de ahorrar combustible, por lo que solo se emplearán los cohetes para el impulso inicial y para frenar ligeramente la caída al final evitando el golpe que dada la rigidez de las patas, queremos evitar.

Todo el resto el trayecto se haría confiando en la gravedad y dirigiendo la nave horizontalmente con micro impulsores que requieren de un menor consumo de combustible. 

¿Como sería la curva? bien, pues básicamente una subida inicial relativamente rapida, una curva de cambio de tendencia relativamente suave dada la baja gravedad, un descenso cada vez más rapido finalizando con un segmento corto plano para representar el frenado en caso de caidas más largas. 

Como estás viendo, es todo una cuestión de plantearse que representamos y diseñar el salto en consecuencia para que la narración sea coherente.

### Un Ent inquieto

O incluso un Mecha, ¿como enfocar esto? bien, la lógica nos dice que un Ent es lento y muy pesado, podría saltar un poquito, pero principalmente imagino que tendría una dura caída en caso de tener la mala suerte de caer al vacío.

Por ello visualizo en mi mente su tabla de salto como una pequeña meseta, una muy ligera curva de salto y caída hasta el punto de altura inicial y desde ahí una bajada casi en picado, para que el motor lo haga caer duramente en caso de "caer al abismo".

Ensayo y error son la clave para dar con la curva que cumpla nuestras expectativas con el mayor grado de precisión posible.

### Un robot ancestral de la superficie de la luna

Este es un caso que puede ser divertido, es una mezcla entre pértiga, ardilla y móulo lunar,

Por un lado es un robot ancestral, eso quiere decir que no llegó ayer ni antesdeayer, por lo que su estructura está pensada para el medio, la lógica me dice que tendrá por tanto algún sistema de pistones emulando las piernas de un saltamontes, lo que le le permite impulsarse casi verticalmente y luego usará algún sistema de giroscopio capaz de permitirle dirigir su caída sin necesidad de frenar debido a que lo que le impulsa también sirve como amortiguador, y dado que está en la luna, la curva de deceleración previa a la caída sería muy parecida a la del módulo lunar... ¡listo!

## Concluyendo

Como veis esto es más un arte que otra cosa, imaginar que haría el personaje y tratar de representar esa lógica con las armas de que disponemos en AGD.

¿Se te ocurren más tipos de personajes posibles con curvas diferentes? dinos cual en los comentarios y si es suficientemente peculiar, ¡la agregaré a la lista!.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no logras conectar, busca cobertura y pasa a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 13 - Manual de uso del Editor de Código ⚫①|Si aún crees en el poder del acero, ve a la página 13]]
* [[Tutorial de AGD 2018 Capítulo 14 - Conectando panallas entre si  ⚫①|Si estás atrapado por el poder de la carne, pasa a la página 14]]
* [[Tutorial de AGD 2018 Capítulo 15 - El salto y sus posibilidades narrativas  ⚫①|Si tienes claro que el poder del contexto es primordial, ve saltando hasta la página 15]]


![[Plantilla - 1MT#One More Thing]]