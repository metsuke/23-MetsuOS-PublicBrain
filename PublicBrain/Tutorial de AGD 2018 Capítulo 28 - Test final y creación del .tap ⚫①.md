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
created: 2025-08-15T00:04:32.067Z
modified: 2025-08-16T12:07:32.714Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 28 - Test final y creación del .tap ⚫①

![JBA Arcade Cabinet](PublicBrain/_resources/05e24fb1662263aece087bd65b2c1d93_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 27 - Editor de Textos y Mensajes ⚫①|<< Anterior]] |  [[Tutorial de AGD 2018 Capítulo 29 - El contexto lo es todo ⚫①|Siguiente >>]]

Tras unos meses desarrollando nuestro juego, es hora de crear, por primera vez, nuestor juego en formato usable por nuestros jugadores.

## ¿Quiere decir esto que acaba el tutorial?

La respuesta corta es <strong>NO</strong>, aún queda mucho por contar.

> NdA 2025, en realidad si, vamos a cambiar de tecnología, pero acabaremos la republicación primero.

Aún hay temas que tratar, tanto del AGD original y de AGDX como de técnicas variadas, pero creo que con el tutorial tal cual es ya podréis crear vuestra primera obra.

Voy a seguir, como digo, creando capítulos, pero en este punto he de diversificar el tipo de artículos de los lunes para poder dar abasto con el proceso de investigacion que requiere contaros lo que viene a continuación.

De no hacerlo así, la calidad bajaría en picado y prefiero espaciar un poco pero llegar con información más sólida en cada entrega.

> NdA 2025 y por eso mismo no lo voy a continuar y, porque no decirlo, vamos a potenciar ZX Game Maker, Prisma y Tuerkas128 en lo que a Speccy se refiere.

Finalmente, quiero tratar temas como el Z80, o ensamblador (al tiempo que aprendo, con el fin de ... bueno, todo en su debido momento), sirva decir que no me basta una semana para delimitar cada tema al 100%.

> Si necesitas información sobre algo, puedes decirmelo en los comentarios, y trato de hacer un capítulo sobre esa cuestión.

## ¡Al lio! lo primero: comprobar, comprobar, comprobar

Antes de nada, hemos de dedicarnos a comprobar todos los aspectos del juego, lo que vamos a generar es un \"entregable\" y ha de ser lo mejor posible, como ejemplo , podríamos hablar de lo siguiente:

* Distancia de Colisión: Hemos de asegurarnos de que está configurada de modo que se adapte lo mejor posible a nuestro juego (Dentro de I - Miscelánea).
* Mapeado: Chequear que todo el mapa esta en su lugar, su aspecto es correcto, las pantallas interconectadas y con sentido...
* Sprites: Hemos de chequear que todos los sprites están perfectamente situados en cada pantalla,con el tipo correcto y que reaccionan apropiadamente.
* Objetos: Comprobar que están en su lugar, que están todos, que su dibujado es correcto.
* Flujo del Juego: Chequear que es posible usar las opciones del menú, que podemos morir, que podemos terminar el juego y se ve la secuencia de victoria... etc.
* Sonidos: Chequear que todo el sonido está correcto, que no quedan sonidos definidos y que no sean usados.
* Teclas: Comprobar que la definición de teclas es correcta, y su respuesta In-Game la esperada.
* En general todo aspecto del juego que se nos ocurra (aunque no lo haya reflejado aquí). Antes de seguir, todo debe estar perfecto.

## Cargar la Loading Screen

El siguiente paso es incorporar la loading screen de nuestro juego, que aparecerá durante el proceso de carga al usuario. Si no tienes una, [te recomiendo que sigas estos tutoriales de Igor Errazking 🌐🟡③](https://www.youtube.com/watch?v=r_t6IBm8-Ac) que te ayudarán a ello.

Para realizar esto, desde el menú principal, se utiliza la opción I - Miscelanea y en el menú que aparece, L - Loading Screen. Una vez cargada, podremos pasar el paso final.

No está de más advertir que debemos crear snapshots (z80 por ejemplo, aunque dependerá de tu emulador) regularmente, máxime en esta fase.

## Grabar en cinta

Para ello, tras introducir nuestra cinta virtual (depende del emulador) o física (si nos ha dado por programar en un Speccy real), pulsaremos la opción G - Save Game.

Se nos pedirá un nombre de fichero, pon el que creas de 8 caracteres.

Acto seguido, se te preguntará si quieres un cargador BASIC, activamos la grabación en la cinta, y tras un par de segundos, le daremos Y, AGD comenzará inmediatamente la grabación. Ahora solo resta esperar.

Una vez que complete la grabación, AGD volverá al menú principal, y tendremos un tap listo para distribuir a amigos y conocidos para que disfruten de nuestra creación.

¿Han hecho algún juego? ¡haganmelo saber para darle un vistazo!
## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no entiendes porque no estamos de .tap-as, ve a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 27 - Editor de Textos y Mensajes ⚫①|Si quieres enviar mensajes a la camarera, para que te traiga unas .tap-as, vé la página 27]]
* [[Tutorial de AGD 2018 Capítulo 28 - Test final y creación del .tap ⚫①|Si no sabes si usar el millon de euros que ganarás con tu juego para .tap-ar agujeros, pasa a la página 28]]
* [[Tutorial de AGD 2018 Capítulo 29 - El contexto lo es todo ⚫①|Si haces .tap .tap .tap con el boli en la mesa, pasa a la página 29]]

![[Plantilla - 1MT#One More Thing]]