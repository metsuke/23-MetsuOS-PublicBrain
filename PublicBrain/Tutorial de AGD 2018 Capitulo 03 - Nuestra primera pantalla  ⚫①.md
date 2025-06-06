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
created: 2025-06-04T20:50:16.259Z
modified: 2025-06-05T12:25:06.049Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 03 - Nuestra primera pantalla  ⚫①

![Mockup de una pantalla de JBA en Amstrad CPC](PublicBrain/_resources/c6240a25f107f33d58a76ce0ca300d86_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 02 - Qué son los tiles ⚫①|<< Anterior]]  | Siguiente >>

Continuamos con el tutorial de AGD en español, en esta ocasión crearemos nuestra primera pantalla, y os propondré el ejercicio artístico que les prometí en [[Tutorial de AGD 2018 Capitulo 02 - Qué son los tiles ⚫①|el capítulo anterior]].

Antes de nada, en este punto dejo definitivamente de "traducir" segmentos del curso original.

El primer capítulo es prácticamente la traducción, en el segundo he sacado absolutamente los pies del tiesto.

Creo que, si bien seguiré los pasos en el orden que se planteó, lo explicaré a mi modo, creo que quedará más natural.

Dicho lo cual, continuamos con el índice de contenidos que planteamos en el capítulo II, en esta ocasión:

- Creación de muros
- Cómo crear plataformas
- Generación de nuestra primera pantalla

## El "Paciente" (la pantalla de AGD)

![Pantalla de la cueva de Javi's Big Adventure](PublicBrain/_resources/0deb0b7ab3e2c4c0f4e5a28e861e92d9_MD5.jpeg)

En la anterior entrega, estuvimos creando los tiles necesarios para dibujar la pantalla que aparece sobre estas líneas, en esta ocasión, lo haremos de verdad.

Vamos a familiarizarnos con el editor de pantallas, y de este modo estar en disposición de dar rienda suelta a nuestra vena artística.

Dejaré para próximos capítulos la parte de muros y plataformas.

## El editor de Pantallas

![El Editor de pantallas de AGD](PublicBrain/_resources/93d89a3d45bc00c2f68cf4cb0f6db69e_MD5.jpg)

Desde el menú principal de AGD, pulsamos la letra C, lo que nos llevará al editor de pantallas.

Globalmente funciona de una forma similar al editor de bloques, pero con un objetivo distinto. Podemos movernos entre pantallas, crearlas, editarlas, borrarlas y - usando los tiles - darles el aspecto que queramos.

En esencia, esta pantalla funciona como un lienzo en el que iremos "estampando" los diferentes tiles hasta formar la imagen deseada, así de sencillo. He aquí las teclas que necesitarás:

```pre
TECLAS
=============================================
- FLECHAS = Mover el cursor de dibujo
- SPACE = "Estampa" el bloque actual en la posición del cursor
- F = Activa/Desactiva el modo de dibujado rápido.
- 1 = Mover a la izquierda por los bloques
- 2 = Mover a la derecha por los bloques
- N = Siguiente Pantalla
- P = Pantalla Anterior
- M = Copiar pantalla actual al portapapeles
- K = Pegar pantalla desde el portapapeles
- X = Crea una nueva pantalla
- D = Borra la pantalla actual
- ENTER = Volver al menú principal.
```
### ¿Cómo usamos el editor de pantallas?

En realidad, el flujo de trabajo es sencillo, en primer lugar, tenemos que ir a la pantalla que queremos editar, si no es la que aparece al entrar, o crear una si es lo que precisamos.

Una vez estemos donde queremos pintar, debemos usar 1 y 2 para seleccionar el tile que queremos dibujar, una vez hecho usaremos las flechas de cursor para movernos y SPACE para dibujar el tile en la posición del cursor.

Hay algunos aspectos a tener en cuenta:

- El tile número 0 es nuestro "fondo" y por defecto aparece llenando toda la pantalla. Si te ha ocurrido que tu pantalla apareció llena de "suelos", ya sabes que debes dejar el tile 0 "vacío". En mi caso usé un cuadro totalmente negro como tile 0 ya que preferí dejar el fondo de un color y evitar así el color clash en la medida de lo posible.
- No existe una tecla para "borrar", para realizar esta acción selecciona el tile 0 y dibújalo sobre las posiciones que quieras borrar.

#### F: Modo de dibujado rápido de pantallas

Si has seguido la máxima de [practicar, practicar, practicar 🌐🟡③](https://www.youtube.com/watch?v=smwXc3vShZw&list=PLmxqg54iaXrijQi4-J9IkAWDEguKRX9Dh), te habrás dado cuenta rápidamente de que crear todo un suelo, o rellenar un área concreta de la pantalla con tiles idénticos es harto tedioso. Para simplificar esta tarea existe la tecla de dibujado rápido, (F), que activa este modo.

Al activar el dibujado rápido, no tendremos que pulsar SPACE para dibujar un tile sino que el tile seleccionado se estampará automáticamente en la posición de cursor al movernos. ¡Pruébalo!

Para desactivarlo, pulsaremos de nuevo la tecla F.

## ¡Ahora a crear!

Una vez te hayas familiarizado con el interfaz del editor de pantallas, te propongo los tres ejercicios siguientes:

1. Recrea en tu AGD la pantalla que estamos usando como ejemplo de la cueva, con los tiles que tú mismo has creado en el capítulo anterior.
2. Crea copias de los tiles que has usado, cámbialos a tu gusto (manteniendo los originales), duplica la pantalla que creaste y modifica la copia para que se dibuje usando tus tiles, no los de "[[MOS Games - The Big Javis Adventure - ZX Spectrum - 2017|The Big Javis Adventure]]".
3. Como BONUS, duplica la pantalla que acabas de crear a tu gusto, y conviértela en una aún mejor obra de arte, añadiendo tiles nuevos para que el aspecto sea del todo espectacular.

Una vez terminadas, deberías tener 3 pantallas distintas:

- Tu copia de la de JBA,
- una versión básica.
- la versión avanzada de la segunda.

### ¡Envía tus creaciones!

Si te apetece, puedes enviarme vía mail a metsuke(at)gmail(Dot)com

Adjúntame tus obras, una breve reseña de qué has dibujado y tu nombre.

Si quieres, puedo publicarlas como ejemplo en este mismo capítulo (si así lo deseas).

## ¡Avanzamos!

En el próximo capítulo crearemos nuestro primer Sprite, orientando nuestro avance hacia el punto de poner un muñeco en pantalla y moverlo, pero por ahora ¡a crear pantallas!

## ¿Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si llegaste aqui producto de una abducción extraterrestre y no tienes claro de que va todo esto, acude al departamento de orientación estudiantil situado en el hall del teatro, y ahi pregunta por la página 1]]
* [[Tutorial de AGD 2018 Capitulo 02 - Qué son los tiles ⚫①|Si has dado de comer al mogwai después de las 12, ¡aprende a prestar atención y vuelve echando leches a la página 2!]]
* [[Tutorial de AGD 2018 Capitulo 03 - Nuestra primera pantalla  ⚫①|Si necesitas llamar a casa, ve a la cabina de la página 3]]
* Si tienes sed, traeme a mi otra lata y espera 2D20+1 horas mientras el mago invoca el contenido
## Referencias Bibliográficas

No se requiere ninguna


![[Plantilla - 1MT#One More Thing]]