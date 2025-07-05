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
created: 2025-06-03T02:52:51.290Z
modified: 2025-07-04T23:33:25.084Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 15
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 02 - Qué son los tiles ⚫①

![Pantalla de Inicio de JBA](/PublicBrain/_resources/f99f121c28c37f1b1f7bd0761189d065_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|<< Anterior]]  | [[Tutorial de AGD 2018 Capitulo 03 - Nuestra primera pantalla  ⚫①|Siguiente >>]]

Continuamos con el tutorial, en esta ocasión centramos la atención en los tiles o bloques.

Si empiezas de cero lee la [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|primera parte de este tutorial de AGD]] antes de entrar a que son los tiles.

En esta ocasión continuamos con el primero de los siguientes elementos (Los tres restantes serán la entrega número 3, por razones de extensión). En conjunto, los cuatro nos permitirán crear nuestro "mundo virtual":

- Bloques (Tiles)
- Creación de muros
- Generación de plataformas
- Diseño de nuestra primera pantalla

Una vez completemos este y el siguiente capítulo seremos capaces de crear pantallas sencillas.

## ¿Qué son los Tiles?

![Pantalla de la cueva de Javi's Big Adventure](PublicBrain/_resources/0deb0b7ab3e2c4c0f4e5a28e861e92d9_MD5.jpeg)

Antes de comenzar a explicar cómo se crean tales en AGD, quizá estaría bien explicar en qué consisten los tiles y qué es eso de "mapas hechos con tiles".

Todo comienza debido a que las máquinas sobre las que ejecutaremos nuestros juegos tienen una memoria extremadamente limitada, así que conviene ahorrar lo más posible.

En la época, los desarrolladores que trataban de grabar las pantallas de sus juegos directamente en memoria, rápidamente se encontraban con el problema de que la memoria del ordenador se llenaba extremadamente rápido.

Por ello, idearon una forma de reducir el espacio que ocupaban sus pantallas.

### "Divide y Vencerás"

Eso reza la famosa máxima, y esto es lo que hicieron, dividir la pantalla en trocitos más pequeños y repetir estos de forma que con un número limitado de trozos de gráfico, un poco de arte y un mucho de paciencia, lograban crear pantallas bastante complejas, con un gasto de memoria mínimo, al tener que indicar solo que en la posición tal, estaba el gráfico cual y no almacenar el gráfico en sí más que una vez.

¿No lo ves claro? Fíjate en el agua de la parte inferior de la captura que acompaña a estas líneas y los pinchos del fondo ¿muchos verdad? En realidad no, tan solo hay un gráfico de 8x8 píxeles para el agua y otro para el pincho, a base de repetir estos dos gráficos he construido ese "lago mortal de la leche"(TM).

Si lo tradujera en texto, en lugar de tener que guardar algo del estilo: **"dibujoagua dibujoagua dibujoagua dibujoagua dibujoagua dibujoagua dibujoagua dibujoagua dibujoagua"** simplemente almacenaremos **"9 x dibujoagua"** lo que evidentemente ahorra cantidades ingentes de memoria para almacenar las pantallas.

```pre
El truco radica en guardar una sola vez el dibujo y repetirlo en lugar de almacenar los píxeles de cada parte de la pantalla, requiere más trabajo para evitar que se note la repetición pero merece la pena.
```

### AGD hay que trabajarlo

Está claro que llegar a crear pantallas vistosas, en las que no se note la repetición de los pequeños bloques (o lo menos posible) y que además sea colorista, no es fácil, pero os enseñaré lo básico para que luego vuestra creatividad os lleve al Olimpo de los creadores de pantallas.

Como me jacto de unir lo viejo y lo nuevo, predicaré con el ejemplo, este video, con un tono muy actual, explica bastante bien cómo funciona esto en la práctica. Hay diferencias entre la época "arcaica" (que es donde haremos nuestro juego con AGD) y la "mona elegante", pero es un modo muy visual de ver esto en la práctica: 


**<iframe width="100%" height="480" src="https://www.youtube.com/embed/SqKqNB4ezJk?si=1eof7u4Nw5xHRL7X" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

Un **pequeño ejercicio**: dedica un rato a tratar de identificar los bloques individuales que he usado para crear el mareado de [[MOS Games - The Big Javis Adventure - ZX Spectrum - 2017|The Big Javis Adventure]] e incluso descárgalo, y usando la versión 4.6 de AGD cargado para ver cómo está hecho, no hay mejor forma de aprender que tocar.

```pre
Si vas a cargar el juego en AGD, te recomiendo que uses la opción cargar de AGD y pongas la cinta del juego a partir del final de la screen.
```

## Creando nuestros primeros tiles en AGD

![Editor de Bloques - Bloque 0 Fondo](PublicBrain/_resources/073300d3399982fa460d948b931193e9_MD5.jpeg)

Lo primero de todo, es acceder al editor de bloques desde el menú principal, pulsando B, esto nos llevará a la pantalla del Editor de Bloques, y mostrará el Bloque 0.

*Este es un bloque muy especial* y que debemos dejar sin tocar.

AGD utiliza este bloque, de tipo "empty space" (lo explicaremos cuando lleguemos a crear paredes y plataformas) que básicamente es el "cielo", o relleno por defecto de todas las pantallas.

Si lo tocamos, variaremos todo el fondo (para bien y para mal).

```pre
Nota importante: Este bloque también define los colores de los sprites, el "paper" de este bloque será el de fondo y el "ink" la tinta. Es algo que sucede "por que se ha diseñado así".
```

En la pantalla del editor podemos ver varios elementos:

- El bloque en tamaño grande, que será donde lo editemos.
- La versión en pequeño para previsualizarlo.
- El tipo de bloque (que trabajaremos en la próxima entrega).
- Una indicación de las distintas tintas y fondos disponibles (los estándar de ZX Spectrum básicamente).
- La indicación del número de bloque que estamos editando.

Os copio aquí la lista de atajos de teclado de esta pantalla:

```pre
TECLAS
=============================================
- FLECHAS = Mover el cursor de dibujo
- SPACE = Cambia color del pixel seleccionado
- Q = Mover a la izquierda por las propiedades
- W = Mover derecha por las propiedades
- N = Siguiente Bloque
- L = Bloque Anterior
- P = Rotar color de Fondo
- I = Rotar color de Tinta
- B = Cambiar Brillo y Flash
- M = Copiar bloque actual al portapapeles
- K = Pegar bloque desde el portapapeles
- C = Limpiar el bloque actual
- X = Crea un nuevo bloque
- D* = Borra el bloque actual
- ENTER = Volver al menú principal.
```

### Bloques, bloques, bloques

Bien, continuemos, en la primera entrega creamos "el área de juego", ahora es el momento de comenzar a llenarla con nuestro "mundo virtual". Como hemos dicho, las pantallas se componen de bloques. Cada uno de ellos de 8x8 píxeles.

Como sabemos en ZX Spectrum, cada "carácter" de 8x8 píxeles puede tener solamente un color de fondo y otro de tinta, por lo que debemos prepararnos para ser creativos.

En esencia es un proceso sencillo, pero lleva práctica. Ya sabéis que [el maestro Fran Gallego nos incita a practicar, practicar y practicar 🌐🟡③](https://youtu.be/9kILDC5TaWA) y aquí vamos a hacer honor a ese guideline!.

### Practicar, Practicar, Practicar

Bien, además de trastear con los distintos bloques, en esta ocasión os voy a plantear un reto. La pantalla de "la cueva" que vemos en este mis post, está construida con 12 tiles distintos.

El reto consiste en identificar esos 12 tiles y replicarlos en el editor de bloques.

Como no es algo sencillo, en caso de que se bloqueen, quieran comprobar si los encontraron, o tengan dudas, pueden preguntarme a través de [Twitter en la cuenta @metsuke 🌐🟡③](https://x.com/metsuke), o por mail en metsuke(at)gmail.com y - en la medida de mis posibilidades y tiempo libre, que no es demasiado - intentaré ayudarles.

En el próximo capítulo usaremos esos bloques para crear la misma pantalla en el editor (por si son curiosos) y a continuación haremos un ejercicio artístico que les revelaré en la próxima entrega :)

Sobre todo, ¡disfruten haciéndolo!.

## ¿Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no lo ves claro, ¡no lo tiles! y pasa a la página 1]]
* [[Tutorial de AGD 2018 Capitulo 02 - Qué son los tiles ⚫①|Si tu madre te ha dicho que tiles la basura, ¡escóndete y huye a la página 2!]]
* [[Tutorial de AGD 2018 Capitulo 03 - Nuestra primera pantalla  ⚫①|Si estas seguro de que lo lógico es que tiles palante, pasa a la página 3]]

<!--espera 2D20+1 horas mientras el mago invoca el contenido.-->

## Referencias Bibliográficas

- PDF de documentacion original de AGD (Incluido en AGD_Starter_Kit_0_3 descargable en el Capitulo 01)  🟡③


![[Plantilla - 1MT#One More Thing]]