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
created: 2025-06-28T20:48:36.132Z
modified: 2025-07-01T20:34:22.916Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 10 - Referencia del Lenguaje ⚫①

![Referencia del Lenguaje en AGD](PublicBrain/_resources/e15232566f2e2de975ea0077d597209d_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 09 - Movimiento estilo Manic Miner ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capitulo 11 - Tipos de Tiles ⚫①|Siguiente >>]]

Como prometí, aquí va la traduccion de la referencia del lenguaje, necesaria para que podamos empezar a hacer cosillas con código.

En el próximo capítulo continuaremos haciendo cositas con nuestro jueguecito, entre tanto... ¡Espero que esta traducción les resulte de utilidad!

## Algunas Teclas del editor

```pre
* SYM-Y Cut line
* SYM-U Paste line
* SYM-Q Home
* SYM-E End
* CAPS-2 Toggle caps lock
* CAPS-3 Delete forward
* CAPS-4 Insert/overtype
* SYM-CAPS Toggle extended mode
* Nota: Las equivalencias de SYM y CAPS son distintas dependiendo de emulador y sistema operativo.
```
## Referencia del lenguaje

Respeto el orden del manual oficial - aunque no me gusta nada como está organizado - para simplificar la búsqueda cruzada y actualización posterior entre ambos documentos.

La base de la traducción es la versión para AGD 4.6, que es la utilizada en este curso (esto es así porque es la versión utilizada en [[ZX Spectrum - The Big Javi's Adventure - 2017|The Big Javi's Adventure]], que sirve como ejemplo vivo y referencia).

> *¡Cuidado!* Es importante destacar que las funciones solo pueden ser usadas tras un IF.

### IF

Comprobación. Si la condición siguiente es verdadera se ejecuta el código existente hasta el END IF.

Puede ser usado con una función, o evaluar variables o parámetros de sprite unos respecto de otros, o respecto de valores numéricos específicos.

### ENDIF

Establece el final de un bloque IF

### LET

Al igual que en el lenguaje BASIC, esta instrucción permite asignar un valor a una variable o a un parámetro de cualquier sprite. El valor asignado puede ser un número o bien otra variable o parámetro de sprite.

### KEY

Función. Espera como argumento un valor numérico de un solo dígito. Si la tecla correspondiente a ese número está siendo pulsada, devuelve true.

### CANGOUP, CANGODOWN, CANGOLEFT, CANGORIGHT

Funciones. Devuelven true si el sprite actual puede moverse arriba, abajo, izquierda o derecha respectivamente.

### LADDERABOVE, LADDERBELOW

Funciones. Devuelven true si el sprite actual puede subir o bajar por una escalera respectivamente.

### Parámetros de Sprite

*X e Y* almacenan las coordenadas en pantalla del sprite actual.

### Variables Globales 

*A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P*

Variables Globales. Cada una de ellas puede almacenar un valor de 8 bits, por lo tanto su valor puede ser cualquier número entero entre 0 y 255 (del rango 0..255).

### SCREEN, LIVES

Variables Globales. Contienen el número de pantalla actual y el número de vidas restantes respectivamente.

### TYPE

Parametro de Sprite. Este valor representa de que tipo es el sprite que está siendo manejado por el código. Se suele usar en conjunción con el parámetro IMAGE. 

Cambiar este parámetro cambiará completamente el comportamiento del sprite, lo cual es util para, por ejemplo, que un enemigo se convierta en un bonus, o bien se detenga y explote para finalmente desaparecer, al recibir un disparo.

No hay razón alguna por la que no se pueda cambiar un sprite a tipo 0 (cero) y ponerlo así bajo el control de jugador, o cambiar el tipo del sprite del jugador por otro que actúe o tenga controles diferentes, la imaginación es tu límite.

Por otro lado, el comportamiento de cada tipo (código de tipo) de sprite, debe ser programado en su evento correspondiente, de lo contrario el sprite se limitará a quedarse ahí quieto, lo cual no está mal si es como quieres que se comporte.

### IMAGE, FRAME

Parámetros de Sprite. 

IMAGE almacena el número de la secuencia de frames (según la numeración del editor de sprites) que representará el sprite en pantalla, y FRAME el fotograma dentro de la secuencia indicada que se muestra actualmente en pantalla.

Con esto puedes cambiar la imagen del sprite en función de la dirección a la que mira, o incluso hacer que \"manejen\" vehículos (en combinación con TYPE) de nuevo sólo estás limitado por tu imaginación.

> *¡CUIDADO!* Establecer FRAME por encima de los existentes para la secuencia actual puede resultar en un sprite dibujado incorrectamente, así que cuidado al manipular manualmente estas variables. Una buena práctica suele ser establecer FRAME a 0 en el mismo momento que cambiamos IMAGE, salvo que exista una razón poderosa para no hacerlo.<br>

### DIRECTION, PARAMA, PARAMB

Parámetros de Sprite.

Puedes usar estas tres variables del sprite actual como consideres oportuno, quizá para indicar en qué dirección se está moviendo un sprite, o en qué fase de su comportamiento está. Son la base para dotar de Inteligencia Artificial a los enemigos.

### ANIMATE

Comando. Anima el sprite activo, rotando automáticamente los frames en sentido ascendente.

### ANIMBACK

Comando. Del mismo modo que ANIMATE, rota los frames, pero en sentido descendente.

### NEXTLEVEL, RESTART

Comandos. Avanza al siguiente nivel y resetea el nivel actual respectivamente.

### SPRITEUP, SPRITEDOWN, SPRITELEFT, SPRITERIGHT

Comandos. Mueve el sprite actual en la dirección correspondiente. No se chequea si hay algún bloque que obstaculice el movimiento o si nos salimos del area de la pantalla. Esa comprobación debe ser realizada previamente mediante instrucciones del tipo CANGOLEFT o LADDERABOVE.

### SPAWN

Comando. Espera 2 parámetros: TYPE e IMAGE. Esto hace aparecer un nuevo sprite con el tipo e imagen especificadas en la posición del sprite actual. El nuevo sprite es creado con FRAME, DIRECTION, PARAMA y PARAMB con valor cero. El Sprite actual no se ve afectado en modo alguno.

### SPAWNED

Comando. Solo debería ser usado tras una instrucción SPAWN. Este comando selecciona el nuevo sprite recién creado. Cualquier código escrito tras este comando se referirá al nuevo sprite. 

Para volver a seleccionar el sprite primario usa la instrucción ORIGINAL. También puedes escribir el código para ese sprite en el evento \"Sprite Initialization\", queda a tu criterio como y donde realizar esta acción.

### REMOVE

Comando. Elimina el sprite actual de la tabla de sprites (la lista de sprites que tiene en cuenta el juego). Útil para destruir enemigos o para la implementación de la recogida de objetos.

### PUTBLOCK

Comando. Requiere como parámetro el número del bloque a dibujar. Este comando dibuja el bloque especificado en la posición LINE y COLUMNS actuales. Puee ser usado para todo tipo de efectos, incluyendo \"abrir\" y \"cerrar\" puertas.

> *¡CUIDADO!* los cambios realizados en la pantalla se perderán si salimos de la pantalla , o tras una instrucción MENU o INV, a no ser que hayas seleccionado la especialización \"Puzzle\" en la configuración del juego.<br>

### COLLISION

Función. Requiere un argumento TYPE. Devuelve true si el sprite actual está en contacto con otro sprite del tipo especificado.

### OTHER

Comando. Solo debe usarse tras una comprobación exitosa de COLLISION. El comando selecciona el sprite con el que hemos colisionado, de forma que cualquier instrucción escrita a continuación afectará a ese otro sprite. Usa ORIGINAL para volver a seleccionar el sprite primario cuando hayas acabado de trabajar con e secundario.

### ORIGINAL

Comando. Se usa tras un comando OTHER o SPAWNED para seleccionar nuevamente el sprite primario.

### ENDGAME

Comando. Finaliza el juego cuando el jugador consigue su objetivo. Esta rutina ejecuta el evento \"Completed Game\". Se ejecutará por ejemplo cuando el jugador consigue pasarse la última pantalla del juego.

El juego solo puede terminar de este modo o cuando el jugador pierde todas las vidas, pero este último caso no ejecuta el evento \"Completed Game\".

### SHOWSCORE

Comando. Muestra la puntuación actual del jugador en la posición actual del cursor. Debe ser precedido por instrucciones para situar LINE y COLUMN en el lugar correcto de la pantalla.

### SCORE

Comando. Recibe un parámetro numérico entero entre 0 y 255, que es la puntuación que se debe añadir a la puntuación total. Por ejemplo SCORE 100 añade 100 puntos.

### SOUND

Comando. Inicia a reproducción de un efecto de sonido con el Chip de sonido AY. Recibe un parámetro numérico correspondiente al sonido a reproducir.

### BEEP

Comando. Reproduce un sonido vía Beeper que comienza bajo e incrementa el pitch. Recibe un único parámetro numérico correspondiente a la duración del sonido.

### CLS

Comando. Limpia la pantalla.

### BORDER

Comando. Recibe un parámetro numérico del rango 0..7, y establece el color del borde correspondiente a dicho valor numérico.

### COLOUR

Comando. Espera un argumento numérico y establece los atributos que se usarán a partir de ee moemnto. La formula que debe usarse para saber que parámetro pasar es:

```basic
128*FLASH + 64*BRIGHT + 8*PAPER + INK
```

 Puede ser usado justo antes de mostrar un texto o antes de limpiar la pantalla.

### DELAY

Comando. Espera un argumento, correspondiente a la duración de la pausa que ejecuta este comando.

### MESSAGE

Comando. Espera un parámetro que indica el número de mensaje que mostrará a partir de la posición actual del cursor.

### KILL

Comando. Inicia la ejecución del evento \"Kill Player\" y resta una vida del contador. Debes inicializar el contador de vidas en el evento \"initialisation\" usando algo del tipo LET LIVES = 3.

### LINE, COLUMN

Variables. Contienen la posición del cursor, a partir del cual se dibujará un texto, o puntuación. Son temporales y cambian cada vez que un sprite es dibujado, así que asegúrate de asignarlos inmediatamente antes de ejecutar un comando MESSAGE o SHOWSCORE.

### GETRANDOM

Funcion. Genera un número aleatorio entre cero y el número indicado como parámetro menos uno, y lo asigna a la variable RND. GETRANDOM 100 obtendrá un valor aleatorio en el rango 0..99. GETRANDOM 2 generará cero o uno.

### RND

Variable. El último número aleatorio generado por GETRANDOM.

### ADD TO, SUBTRACT FROM

Comandos. Suma o resta un valor numérico de una variable o parámetro de sprite. Por ejemplo ADD 1 TO A añade 1 a la variable A, y SUBTRACT 5 FROM B restará a su vez 5 al valor contenido en B.

### DISPLAY

Comando. Muestra el valor numérico en la variable o parámetro que se indica. Por ejemplo DISPLAY LIVES mostrará el número de vidas (en la posicion actual del cursor).

### SCREENUP, SCREENDOWN, SCREENRIGHT, SCREENLEFT

Comandos. Cambia a la pantalla superior, inferior , derecha o izquierda según el mapeado definido, si es posible.

### DEADLY

Función. Devuelve true si el sprite actual está en contacto con un bloque mortal.

### CUSTOM

Funcion. Similar a DEADLY, devuelve true si el sprite actual está en contacto con un bloque de tipo custom.

### WAITKEY

Comando. Espera la pulsación de una tecla.

### JUMP

Comando. El sprite actual saltará, siempre y cuando no esté ya en e aire y que no haya bloques que lo impidan. Como podrás imaginar, se puede hacer saltar a cualquier sprite, no sólo a aquellos bajo el control del jugador.

### FALL

Comando. Si el sprite no está ya cayendo o saltando, este comando comprueba si el sprite está sobre algo sólido. Si no lo está, empezará a caer, usando la mitad descendente de la tabla de salto (no te preocupes, aunque hayas modificado la tabla, el juego lo calculará automáticamente). FALL es útil para cualquier sprite que esté sujeto a gravedad, como en un juego de plataformas.

### GOT

Funcion. Se usa en el contexto de un IF y espera un argumento único. Devuelve true si el objeto indicado está en posesión del jugador. El argumento puede ser una variable si es necesario de modo que tan válido es IF GOT 1 como IF GOT A (_NdT. ya estamos con el Abú Simbel xD_). Puedes incluso pasarle un parámetro de sprite si lo deseas.

### GET

Comando. Espera un parámetro especificando el objeto a obtener. Coloca el objeto especificado en el inventario del jugador, con independencia de donde esté. El objeto puede estar en la misma pantalla, en otra , o simplemente perdido. Queda a tu criterio decidir cuando el jugador puede obtener un objeto en particular. En otros casos te puede interesar usar DETECTOBJECT para determinar si el sprite está tocando un objeto antes de ejecutar esta instrucción.

### PUT

Comando. Requiere un argumento que especifica el número de objeto. El objeto es colocado en pantalla justo en la posición del sprite y eliminado del inventario del jugador, salvo que el objeto ya esté en la pantalla actual. El argumento puede ser un número, variable, o parámetro de sprite.

### DETECTOBJ

Comando. Detecta los objetos que están en contacto con el sprite actual, y coloca el resultado en la variable OBJ. Si el sprite está tocando varios objetos, solo se detectará el de identificador más bajo. Si no se detectan objetos, se indica asignando 255 a OBJ.

### OBJ

Variable. El último número de objeto detectado por DETECTOBJ o 255 si no se detectó ninguno.

### CLOCK

Variable de solo lectura. El contador de frames actuales, en cincuentavos de segundo. Útil para ajustar la ejecución de tareas en múltiples frames.

### MENU

Comando. Requiere un argumento especificando el número de mensaje. Crea un menu pop-up en el centro de la zona de juego, donde las opciones son tomadas a partir de ese mensaje, cada uno en su propia línea. El jugador podrá entonces seleccionar una opción usando arriba abajo y disparo. 

Habitualmente esto puede ocurrir cuando el usuario pulsa cierta tecla. Sin embargo, puede ocurrir en cualquier otro evento de sprite, por ejemplo, cuando un sprite colisiona con el jugador. Podrías mostrar un mensaje - la conversación del sprite con el jugador - y luego usar MENU para pedir una respuesta. La pantalla se redibuja tras la selección de la opción por parte del jugador.

### INV

Comando. Requiere un argumento especificando un número de mensaje, que es el que contiene los nombres de los objetos. Similar a MENU pero genera un menú basado en los objetos que el jugador posee, mostrando una lista vertical con sus nombres. Útil para seleccionar un objeto para procesar o dejar. INV solo funciona con la especialización \"Adventure\".

### EXIT

Comando. Sale inmediatamente del evento actual interrumpiendo cualquier procesamiento que se esté llevando a cabo en el.

### REPEAT

Comando. Requiere un parámetro que determina el número de repeticiones. El código a partir esta instrucción y hasta el siguiente ENDREPEAT se repetirá el número de veces especificados.

El código dentro de un bloque REPEAT es indentado automáticamente para mejorar la legibilidad.

*¡Cuidado!* REPEAT no puede ser anidado.

### ENDREPEAT

Comando. Establece el final de un bloque de código REPEAT. 

### MULTIPLY BY

Comando. Multiplica un parámetro de sprite o variable. Por ejemplo MULTIPLY C BY 7.

### DIVIDE BY

Comando. Divide un parámetro de sprite o variable. Por ejemplo DIVIDE Y BY 8.

### SPRITEINK

Comando. Establece la tinta del sprite actual al color especificado. Por ejemplo SPRITEINK 4 o SPRITEINK PARAMB. No afecta a PAPER, FLASH o BRIGHT.

Para evitar dejar un rastro de tinta de colores, debes resetea el SPRITEINK al comienzo de cada evento de sprite. Si tu tinta para sprites habitual es 7 (blanco), te puede interesar usar SPRITEINK 7 al comienzo del evento de sprite, mover el sprite y luego establecer el color con que quieres que se dibuje.

En el caso de objetos estáticos recolectables, solo debes resetear el SPRITEINK al color por defecto cuando son recogidos. ([Revisa como está programado en el juego Diamond Geezer para ver un ejemplo](https://stardot.org.uk/forums/viewtopic.php?t=16535\)). _NdT: Creo que el juego del enlace pero no estoy seguro._

### LASER

Comando. Espera un argumento numérico. Dispara un láser a izquierda o derecha desde la posición actual del sprite, dependiendo del parámetro. Parámetros pares hacen que dispare hacia a izquierda, los impares a la derecha. 

La colisión de un sprite con un láser puede ser detectada desde el evento del sprite usando IF COLLISION 10. LASER solo funciona si la especialización de partículas es seleccionada en el menú miscelánea.

### TRAIL

Comando. Útil para general \"polvo de hada\" o \"rastros de vapor\". TRAIL crea un rastro vaporoso a base de partículas en el centro de la posición del sprite actual. 

Usando ADD 8 TO Y o SUBTRACT 8 FROM Y antes de ejecutar TRAIL, puedes generar un rastro a izquierda o derecha del sprite. Recuerda volver a dejar Y como estaba tras ejecutarlo para evitar efectos extraños en la posición del sprite. Solo funciona con la especialización \"Particle\".

### EXPLODE

Comando. Requiere un argumento numérico que especifica el número de partículas. Crea una explosión en la posición del sprite actual. Usado junto a REMOVE, EXPLODE elimina la necesidad de dibujar una animación para la explosión de tus sprites. 

Si olvidas indicar el parámetro numérico, la siguiente instrucción fallará al compilar. Si olvidas REMOVE, tu sprite no desaparecerá y te quedaras pensando en porqué el sprite ha explotado y sigue en la pantalla. Solo funciona en la especialización \"Particle\".

### FADE

Comando. Oscurece progresivamente la ventana hasta que queda totalmente negra. FADE solo funciona con la especialización \"Effects\" activada.

### TICKER

Comando. Muestra un mensaje en LINE y COLUMN actual, y hace scroll con él al pixel.Espera dos parámetros, el primero es el número de mensaje y el segundo es el ancho del área visible del mensaje en caracteres.

TICKER continua y repite el mensaje cuando llega al final. TICKER 1 16 mostrará el mensaje 1 en un area de la mitad del ancho de la pantalla. Para detener TICKER especifica un número de mensaje que no exista, por ejemplo TICKER 99 1. Solo funciona con la especialización \"Effects\" activa.

### BIGMESSAGE

Comando. Requiere un parámetro especificando un mensaje. Muestra ese mensaje en la pantalla con una fuente de doble altura. Solo funciona con la especialización \"Effects\" activa.

### REDRAW

Commando. Redibuja a pantalla, los sprites, los objetos y las partículas. Si estás creando una aventura arcade, puede interesarte mostrar un mensaje en el area de juego, esperar una tecla con WAITKEY y luego hacer REDRAW antes de retomar la acción.

### SILENCE

Comando. Silencia el chip de sonido AY.

### CONTROLMENU

Comando. Util para el evento de menú/intro. CONTROLMENU espera que el usuario elija una opción para seleccionar el tipo de control. Las opciones son 1 para teclado, 2 para joystick Kempston y 3 para joystick Sinclair (tecla 67890).

### DIG

Comando. Espera un parámetro del rango 0..3 especificando la dirección arriba, abajo izquierda o derecha respectivamente. Elimina los bloques FODDER inmediatamente adyacentes al sprite del jugador (en la dirección indicada). Solo disponible con la especialización \"Adventure\" activa.

### STAR

Comando. Parte del engine de partícuas. STAR crea un campo de estrellas vertical u horizontal cuando es llamado repetidamente. Espera un parámetro que indica la dirección, 0 para vertical o 1 para horizontal. Solo funciona con la especialización \"Particles\" activa.

### BIGSCORE

Comando. Funciona igual que SHOWSCORE, pero muestra el mensaje en pantalla con texto el doble de alto. Solo funciona con la especialización \"Effects\" activa.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si te acaba de caer el libro en la cabeza, y estás en estado de shock, pasa a la página 1]]
* [[Tutorial de AGD 2018 Capitulo 10 - Referencia del Lenguaje ⚫①|Si aun buscas referencias en el lenguaje, continua estudiando, con buena músuca, en la página 10]]
* [[Tutorial de AGD 2018 Capitulo 11 - Tipos de Tiles ⚫①|Si ya has "Terminao-To", busca a Sarah Connor para que te entrene para sobrevivir a la rebelión de Vegatrón en la página 11]]


![[Plantilla - 1MT#One More Thing]]