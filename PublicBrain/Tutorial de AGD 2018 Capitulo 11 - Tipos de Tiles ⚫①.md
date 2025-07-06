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
created: 2025-07-01T20:26:20.518Z
modified: 2025-07-06T19:48:46.619Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 11 - Tipos de Tiles ⚫①

![ZX-Uno nuestro cohete](PublicBrain/_resources/05b4e96ee345689a7621f056fdd54bff_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 10 - Referencia del Lenguaje ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capitulo 12 - Cargar juegos de AGD desde cinta|Siguiente >>]]
 
Hasta ahora hemos dibujado los tiles, [[Tutorial de AGD 2018 Capitulo 04 - Los Sprites aka creando el Muñequito y los Bichos ⚫①|creado sprites]], incluso hemos [[Tutorial de AGD 2018 Capitulo 08 - Mover a nuestro protagonista por la pantalla ⚫①|puesto a nuestro protagonista en pantalla]], pero hay un pequeño detalle que aún no hemos cubierto: el personaje no interactúa con el escenario. En el capítulo de hoy vamos a remediar esto.

## Posicionando Sprites

Cuando estuvimos jugando por primera vez con nuestro protagonista en pantalla, pudimos observar dos cuestiones: una, la ya mencionada, que el muñeco no interactua lo más mínimo con el escenario y otra, que aparece en el centro de la pantalla, y no necesariamente esto ha de coincidir con lo que es "lógico" en el escenario que hemos diseñado para el.

Por suerte solo necesitamos explicarle a AGD donde queremos que aparezca nuestro protagonista (más adelante usaremos esta misma función para situar los enemigos), y para ello accedemos desde el menú principal a la opcion N - Sprite Positions, lo que nos mostrará un interfaz similar al siguiente, en la que nuestro protagonista aparecerá marcado.

![Pantalla de la opcion Sprite Positions de AGD en la pantalla inicial de Javis Big Adventure](PublicBrain/_resources/f523898f445c2ce85cac7abb9e5046d0_MD5.jpg)


En la pantalla se nos mostrará el escenario y sobre él los diferentes sprites que hay situados en el, en la parte superior (que no se ve en la imagen anterior) nos muestra el tipo de sprite asociado al que está actualmente seleccionado. 

El tipo 0 representa sprite controlado por el usuario, el resto son de uso libre (del 1 al 9), la diferencia entre los tipos es que cada tipo ejecutará el evento asociado a su número, en el cual podremos programar comportamientos específicos para cada tipo. Ya veremos cuando creemos los enemigos como funciona, no te preocupes ahora nada más que del prota de nuestro juego. Antes de seguir, aquí van las teclas que se usarán en esta pantalla:

```pre
TECLAS PARA SPRITE POSITIONS
=============================
- N - Pantalla Siguiente
- P - Pantalla Anterior
- Q - Seleccionar sprite siguiente
- I - Cambiar imagen del sprite
- T - Cambiar tipo del sprite
- D - Eliminar sprite actual de la pantalla
- X - Añadir nuevo sprite a la pantalla
- Cursores - Mover el sprite seleccionado.
```

## Configurando el escenario

Una vez colocado nuestro sprite protagonista en su posición correcta (al menos sobre el suelo xD), vamos a ver como dotar de interacción al escenario.

El concepto detrás de esta funcionalidad en AGD es muy sencilla, cada uno de los tiles o bloques que forman parte de la pantalla, tiene asignado un tipo, por defecto son casi como los neutrinos, esto es no interactúan con nada (los neutrinos con casi nada casi siempre) son absolutamente atravesables en cualquier dirección.

Ejemplos de esto último es el tile 0 que es el relleno por defecto, y que suele ser de este tipo, de forma que el sprite "lo atraviesa", otros, como veremos, ofrecen diferentes tipos de características que en conjunto construyen un "mundo coherente" para nuestro personaje.

## Tipos de Bloque

Sirva decir que en la [[Tutorial d'AGD 2018 Capítol 02 - Què són els tiles ⚫①|pantalla de bloques]], se usa a tecla W para cambiar el tipo de un bloque al siguiente y Q para cambiar al anterior tipo.

* *Empty Space (Espacio Vacío)* - Básicamente eso, espacio vacío que los sprites (no solo el protagonista) atravesará sin problemas.
* *Platform (Plataforma)* - Lo que todos entendemos por plataforma, no se puede atravesar de arriba hacia abajo, ni lateralmente, pero si de abajo hacia arriba.
* *Solid Wall (Muro Sólido)* - El tile no puede ser atravesado en ninguna dirección, como su propio nombre indica
* *Ladder (Escalera)* - Determina que el bloque forma parte de una escalera, mostraremos como funciona en un monográfico más adelante.
* *Fodder (Excavable)* - Determina que el bloque actual es un bloque excavable, está [[Tutorial de AGD 2018 Capitulo 10 - Referencia del Lenguaje ⚫①|relacionado con la instrucción DIG y el modo aventura]].
* *Deadly (Mortal) - Establece un bloque que "mata". Si el jugdor lo toca morirá automáticamente, muy útil para lava, o agua en juegos tipo Dizzy.
* *Custom (Personalizado)* - Establece un bloque personalizado, con el que podremos jugar a través de código. Sirva como ejemplo que las partes en que "nadas en el aire" o subes enredaderas en [[MOS Games - The Big Javis Adventure - ZX Spectrum - 2017|The Big Javi's Adventure]], están hechos con este tipo de bloque. Merecen  su propio monográfico que llegara, adivinad, más adelante xD.
* *Water (Agua)* - Bueno, hace eso, convertir el bloque en agua. A efectos prácticos eso significa que si el personaje no "hace pie" , se hundirá lentamente, y tendremos que pulsar la tecla de salto para subir. Por otro lado el entorno es más gelatinoso que el aire y por tanto AGD simulará esto, izquierda y derecha funcionarán de forma similar. Asi hice las zonas acuáticas y la cascada "escalable".

Ahora es tu turno, toma los tipos de bloque y configure la pantalla correctamente, una vez hecho, prueba a recorrerla con el prota y ver qué ocurre. En próximos capítulos veremos como graduar el salto y algunas cosillas extra, pero eso - no lo adivinaran nunca - más adelante. Disfruten no solo haciendo lo que les indico, sino jugando sin miedo, que es como más se aprende.

## Bonus

¿Se atreven con más? inventen un funcionamiento original para un bloque custom y traten de hacer la realidad, ¿flotar por el espacio?¿quizá una seta en la que el jugador "bote" como en sonic?¿una zona arenosa en la que el jugador se mueva más despacio? échenle imaginación y ¡mandenme sus efectos!

Por cierto, no quiero marcharme sin dejarles un video de uno de los juegos de Dizzy, para que puedan ver a qué me refiero con lo de bloques de agua mortales, ¡tan icónico como las famosas gotas! :)

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/HEuaKu0r3o4?si=-kpHwRAHHCNQvFOa" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si te has quedado atascado diciendo "Mi caaaasa , teleeefono", pasa a la página 1]]
* [[Tutorial de AGD 2018 Capitulo 10 - Referencia del Lenguaje ⚫①|Si te empieza a gustar el reggaeton, estamos haciendo algo mal, vuelve a la página 10]]
* [[Tutorial de AGD 2018 Capitulo 11 - Tipos de Tiles ⚫①|Si lo tiles como lo tiles el personaje sigue cayendo a través de las plataformas, revisa nuevamente la página 11]]
* [[Tutorial de AGD 2018 Capitulo 12 - Cargar juegos de AGD desde cinta|Si no entiendes porque un huevo puede "tilarse" desde las nubes y rodar sin romperse, unete al equipo de reflexiones sin fronteras mientras buscamos la solucion en la página 12]]

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

![[Plantilla - 1MT#One More Thing]]