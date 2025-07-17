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
created: 2025-07-14T11:35:37.637Z
modified: 2025-07-17T07:08:52.319Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 14 - Conectando panallas entre si  ⚫①

![Varias pantallas de JBA interconectadas](PublicBrain/_resources/92ffd47eca16e3291db020d84b79f549_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 13 - Manual de uso del Editor de Código ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capítulo 15 - El salto y sus posibilidades narrativas  ⚫①|Siguiente >>]]


En un capítulo anterior, [[Tutorial de AGD 2018 Capitulo 11 - Tipos de Tiles ⚫①|estuvimos viendo como indicar a AGD el rol de cada tile , creando suelos, plataformas y zonas mortales]]. En esta ocasión vamos a interconectar pantallas en las cuatro direcciones.

AGD admite hacer un juego en el que "pases pantallas" a lo Bubble Booble o Snow Bros, y eso lo comentaremos cuando empecemos a hacer juegos de otros tipos, de hecho cuando termine publique y posteriormente os comente como está hecho C5 Juanje's Revenge mi siguiente juego y que va con un retraso monumental, pero que quizá continuaré como parte del Tutorial en el futuro.

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/2o8mpCoPGxY?si=lHY7T7j4b3ulFp-k" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

```pre
Si, ya sé, ya sé, iba a salir en 2018 xD, no voy a entrar a explicar la dificultad creciente de nuestras vidas según envejecemos, tenemos que cuidar hijos, sobrinos y padres, y todo lo que supone la vida adulta. 

Solo diré que tengo previsto retomarlo, a pesar de que en su dia perdí la versión de desarrollo que estaba como al 80% de completarse y respiraré hondo para rehacerlo.
```
## Soy el mapa, el mapa, el mapa

Lo primero, antes de hacer que nuestro protagonista recorra las pantallas, es configurar el mapa, ya sabéis como funciona, lo que no sé si os comenté en su momento es que podéis indicar en qué pantalla debe comenzar el protagonista seleccionando una de las pantallas del mapa y pulsando X.


![Editor de Mapas con la pantalla de la cascada seleccionada](PublicBrain/_resources/bfd08c33b5100c26550f8f6c0a3ffbd4_MD5.jpeg)

En la imagen anterior podéis apreciar el bloque de pantallas 00 - 01 en la fila superior y 07-02 en la inferior, que corresponden con las pantallas que se ven en la imagen que encabeza este capítulo.

Un detalle obvio, además de crear e insertar las pantallas en el mapa, las aberturas y paredes entre ellas deben ser coherentes. Por cierto, <a href="https://maps.speccy.cz/map.php?id=BigJavisAdventure&sort=4&part=2&ath=">aquí podeis consultar el mapa al completo  🌐🟡③</a>.

## Engarzando pantallas

Como decía , las aberturas deben ser coherentes si hay hueco para pasar hacia la derecha de la pantalla 1 a la 2 a determinada altura, debe existir el hueco equivalente en la parte izquierda de la 2 para poder regresar, a no ser que exista algún motivo en la mecánica o el argumento por el que no deba ser de este modo.

Lo mismo sucede con las partes superior e inferior de las pantallas que se comuniquen a través del "suelo" y "techo", el hueco debe ser coherente, y estar indicado, salvo en los casos en que - como sucede por ejemplo con el acceso a las pantallas de las nubes - se quiera "mantener en secreto" para darle algo de emoción al asunto en determinadas zonas del mapeado. Cuestión de imaginación.

Recordemos que si el personaje supera el margen izquierdo aparecerá en el derecho y lo mismo sucede con arriba y abajo, para dotar de coherencia al mapa, es necesario limitar con paredes, suelos o techos el avance del personaje para que no cambiemos de pantalla donde no se debe. 

En las pantallas en que "el cielo es el límite", hay por ejemplo bloques de tipo pared con aspecto de cielo, para evitar este problema en aquellos lugares donde el salto máximo supera el margen de la pantalla.

## El mecanismo del cambio de pantalla

Antes de discutir el código en sí, me gustaría explicar como logramos el efecto de "cambiar de pantalla" de modo que el jugador perciba continuidad.

En esencia, cuando cambiamos de pantalla con SCREENLEFT o SCREENRIGHT por ejemplo, lo único ue sucede es que desaparecen los sprites de la pantalla actual, se cambia el escenario al correspondiente según el mapa y se ponen en pantalla los sprites de la nueva.

Quizá sea algo decepcionante, pero lo único que sucede es que "cambiamos el escenario", cuan titiriteros que cambian el fondo para mostrar que caperucita está en el bosque.

Pero claro está queda nuestro protagonista, si sólo cambiamos el fondo, resultará que el personaje quedará situado en una posición incorrecta, es por ello que cuando vamos a la pantalla de la derecha, además de cambiar el fondo, movemos el personaje al lado que le corresponde en la pantalla destino. Todo sucede tan deprisa que para el jugador el muñequito ha ido andando a otra pantalla, pero, en realidad, es como un escenario teatral. X metros cuadrados y ya xD.

Antes de ver código, arranquen el juego y cambien de pantalla ahora que saben lo que ocurre realmente y fijense en lo que sucede realmente.

## El Código "Mágico"

Entre los tipos de tiles y esto, estoy destrozando vuestro recuerdo de la infancia, resulta que todo es una obra de teatro bien sincronizada. No hay motivo para entristecerse, ahora que empezáis a vislumbrar como funciona, podreis apreciar aún más el trabajazo de los desarrolladores de la época, [[Noticias - Cinco Duros anuncia la primera serie documental sobre la industria del videojuego español - 2025-05-30 🟡③|y ellos no tenían ni internet, ni AGD]]

Vamos al lío, lo primero, tengamos en cuenta que los pixeles en AGD se cuentan con un sistema de coordenadas cartesianas cuyo punto de origen es el pixel superior izquierdo de la pantalla.

Aquí va el código, no está todo el del evento de movimiento del jugador, sólo las partes relevantes.

```BASIC
...
        IF Y > 167
          SCREENRIGHT
          LET Y = 6
          EXIT
        ELSE
        ...
        IF Y < 8
          SCREENLEFT
          LET Y = 168
          EXIT
        ELSE
        ...
```

Es [[Tutorial de AGD 2018 Capitulo 08 - Mover a nuestro protagonista por la pantalla ⚫①|el mísmo código que vimos cuando movíamos al protagonista de nuestro juego por primera vez]], solo que ahora somos más conscientes de lo que sucede en realidad.

En esencia cuando movemos a la derecha, y se supera el pixel 168 pasamos a la pantalla de la derecha (el proceso del fondo y los sprites lo realiza AGD, sólo hemos de decirle [[Tutorial de AGD 2018 Capitulo 07 - Editor del Mapa ⚫①|que pantallas hay y como están situadas, en el Mapa]] y ajustamos la posición del protagonista.

## Todo lo que sube baja, y viceversa

¿Que pasa con arriba y abajo?, aunque el código de tipo Manic Miner no lo contempla, veamos como gestionar esto:

```BASIC
...
        IF KEY 3
          JUMP
        ENDIF
        ...
        IF X <= 16
          SCREENUP
          LET X = 128
        ENDIF
        ...
        FALL
        IF X > 128
          SCREENDOWN
          LET X = 17
        ENDIF
        ...
```

Básicamente integramos las comprobaciones para el cambio arriba y abajo en el flujo que controla el salto y la caida, de este modo si "nos dejamos caer" bajaremos a la pantalla inferior y si saltamos por encima del límite de la pantalla, cambiaremos a la superior.

>*¡Cuidado!* cuando diseñemos el mapa tengamos en cuenta que para subir hemos de poder saltar y caer en un área sólida por encima del límite inferior de la pantalla a la que accedemos mediante el salto.

Antes de programarlo en sus proyectos, prueben a cambiar de pantalla arriba y abajo en JBA para observar el funcionamiento del proceso.

En el próximo capítulo trataremos la configuración del salto y las diferentes posibilidades narrativas que este nos ofrece, hasta entonces ¡no olvidéis practicar, practicar y practicar!.
## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no logras conectar, busca cobertura y pasa a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 13 - Manual de uso del Editor de Código ⚫①|Si aún crees en el poder del acero, ve a la página 13]]
* [[Tutorial de AGD 2018 Capítulo 14 - Conectando panallas entre si  ⚫①|Si estás atrapado por el poder de la carne, pasa a la página 14]]
* [[Tutorial de AGD 2018 Capítulo 15 - El salto y sus posibilidades narrativas  ⚫①|Si tienes claro que el poder del contexto es primordial, ve saltando hasta la página 15]]

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  


![[Plantilla - 1MT#One More Thing]]