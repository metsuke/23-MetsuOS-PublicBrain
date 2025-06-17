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
created: 2025-06-11T16:26:25.753Z
modified: 2025-06-17T14:27:49.231Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 6
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 05 - Animando sprites ⚫①

![Los lemmings estilo monty python en diversas posiciones y colores](PublicBrain/_resources/94373ec992915b406d15e7d2c4c2b131_MD5.jpg)
* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 04 - Los Sprites aka creando el Muñequito y los Bichos ⚫①|<< Anterior]]  | [[Tutorial de AGD 2018 Capitulo 06 - Importar Sprite Sheets ⚫①|Siguiente >>]]

[[Tutorial de AGD 2018 Capitulo 04 - Los Sprites aka creando el Muñequito y los Bichos ⚫①|En el capítulo anterior, comentábamos los fundamentos de manejo del editor de sprites de AGD]], en esta ocasión querría centrar mi atención en la animacion de sprites.

Puede parecer una cuestión baladí, pero personalmente creo que el 50% de la conexion con un juego se produce debido a la calidad de la animación (⚫①) , imaginen sino una película de Disney con animaciones estilo South Park... digno de verse sin duda, pero esa magia que hace que los más pequeños de la casa empaticen con los personajes se esfumaria inmediatamente.

He de hacer constar que yo no soy animador, por lo que no puedo dar clases al respecto, es por ello que he dedicado un tiempo a localizar y seleccionar algunos contenidos que, estudiados con atención, pondrán en contexto mis comentarios posteriores, y espero ayuden con ello a comprender el proceso de forma general, así como dar a conocer recursos excelentes que ya existen en la red.

## Material de Estudio

En primer lugar os propongo un [video de Adderly Céspedes 🌐🟡③](https://www.youtube.com/watch?v=yVngSlsMEk8) (Es un gran canal, os recomiendo darle un vistazo) de cómo se anima "actualmente", aunque no tenga que ver con AGD si nos pone en contacto con aspectos generales de la animación (y de la creación de sprites), con el resto del contenido iremos acercándonos a las limitaciones de un ordenador de 8Bits.

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/yVngSlsMEk8?si=eN55bxHlAPh27Kox" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

Una vez tengáis claro el concepto general, avanzamos [siguiendo este espectacular tutorial que muestra el proceso de creacion y animacion de sprites ya usando pixels 🌐🟡③](http://www.pixelsmil.com/2012/04/crear-y-animar-un-sprite-tutorial-paso.html), aunque sin un limite de tamaño y colores como el que tendremos en Speccy.

[Una herramienta que podeis usar es esta llamada Pixela 🌐](https://2ddentertainment.com/products_pag/p0006.htm) que yo también estoy testeando (en una maquina virtual Windows) porque no encuentro nada potente para Mac.
## ¡Ahora exprimamos AGD!

Hay que tomar en consideración que estamos ante un entorno 8Bits, con unas limitaciones a nivel de color bastante duras, no solo por la máquina sino por cómo funciona el entorno de AGD. Para no marear con cuestiones tecnias sirva decir que los sprites son de un color determinado (todos, aunque luego se pueda jugar por codigo) y solo de uno, o todo el sprite es blanco o todo es rojo, por ejemplo, lo cual nos obliga a ser ingeniosos.

Lo que no podemos expresar con colores, en Spectrum se suele expresar con pixels separando áreas o delimitando objetos, es obvio que la limitación es grande, pero se pueden lograr cosas muy chulas. Ejemplo de esto de "dejar huecos" es el sprite de las antorchas que uso en el juego, en otras plataformas usaríamos amarillos y rojos en la llama, o tonos metalicos o tierra para el portaantorchas, aquí al tener un solo color, hemos de recurrir a eso de pintar o no pintar un pixel. Requiere tiempo pero no s tan complicado como pueda parecer.

![Sprite de la llama](PublicBrain/_resources/b3bbeaa2d42affc8f37f1ebf347588b8_MD5.jpeg)

Y lo mismo sucede por ejemplo con este gráfico de uno de los enemigos, en lugar de pintar lineas de color para separar los elementos, dejamos líneas sin dibujar. Esto tiene el hándicap de que reduce los ya escasos pixeles con que contamos, pero ahí está la parte en que cada uno hemos de desarrollar nuestro arte con la práctica. De hecho, aunque el resultado pueda no ser mejor que el de un profesional, es la parte que más disfruto de la creación de mis propios juegos, el expandir mis propias capacidades creando algo mejor que lo que era capaz de hacer anteriormente.

![Sprite Nave Enemiga](PublicBrain/_resources/c523a9ddf4680d84637f7c3f5c2c1a7e_MD5.jpeg)
## Frames, frames, frames

Como comentamos en [[Tutorial de AGD 2018 Capitulo 04 - Los Sprites aka creando el Muñequito y los Bichos ⚫①|el capítulo 4 de este curso]], se pueden crear varios frames por cada sprite, la secuencia de estos es lo que dotará de vida a nuestras creaciones, según creemos varios frames de animación, podremos pulsar f a la velocidad que deseemos para ver la animación en el cuadro en que editamos el sprite. Mas adelante veremos como verlo en el escenario pero por ahora usaremos este método.

Hemos de tomar en consideración que, en una maquina de estas características no solo los colores son limitados, la velocidad de la máquina también así como la memoria. Si usamos demasiados frames, la animacion sera genial pero ocupara muchisima memoria y tardara mucho en ejecutarse, por el contrario si usamos demasiado pocos, la animacion ira a saltos y nuestro personajes parecera congelarse continuamente como en un videojuego online cuando hay cortes de conexión.

Personalmente suelo usar 3 máximo 4 frames en los casos más extremos, para equilibrar, y tambien me he fijado muchiiiiiisimo en los graficos de animaciones Japonesas de la epoca, en gran medida en los RPG de 8 y 16 bits que solian animar con mucho arte usando a veces solo dos frames. 

> [No hay mas secreto que practicar, practica y practicar](https://www.youtube.com/channel/UCSdIAKvPxlB3VlFDCBvI46A), como dice siempre el maestro profesor Retroman.

## Menos es Mas

Os pongo a continuacion los cuatro frames de los mini lemmings de JBA, quisiera con ello trasmitir una ultima cuestión en este capítulo y es que cuando las limitaciones son tan grandes hay que jugar con la imaginacion del jugador, así como optimizar la animacion, dotando del mayor carisma posible a nuestras creaciones. Si yo, que soy un perfecto novato, he logrado crear unos mini personajes con muy pocos pixeles, seguro que tu también puedes, y recuerda, esto lo hacemos por diversión, así que cero verguenza y cero miedos, la única competición es contra nosotros mismos para ser mejores cada vez.

![Animacion de los Lemmings, usando una ligera vibracion para enfatizar el objetivo de la animación](PublicBrain/_resources/4fc5f1e5ed8dd95a2330e052bf8ad85a_MD5.gif)

En el próximo capítulo exploraremos la importación de spritesheets en forma de screens y más adelante empezaremos a usar los sprites en la pantalla que creamos. Mientras tanto !disfruten creando sus propias animaciones!

## ¿Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si tienes miedo, ve a esconderte a la página 1]]
* [[Tutorial de AGD 2018 Capitulo 05 - Animando sprites ⚫①|Si has logrado entrar en la sala de entrnamiento de Goku, quedate un par de años en la página 5]]
* [[Tutorial de AGD 2018 Capitulo 06 - Importar Sprite Sheets ⚫①|Si quieres ir al instructor de clase y aprender 'Invocar Sprite Sheet' pasa a la página 6]]

## Referencias Bibliográficas

*  [Video de Adderly Céspedes sobre las bases de la animación de sprites 🌐🟡③](https://www.youtube.com/watch?v=yVngSlsMEk8)
* [Tutorial que muestra el proceso de creacion y animacion de sprites usando pixels en pixelsmil.com 🌐🟡③](http://www.pixelsmil.com/2012/04/crear-y-animar-un-sprite-tutorial-paso.html)

![[Plantilla - 1MT#One More Thing]]

