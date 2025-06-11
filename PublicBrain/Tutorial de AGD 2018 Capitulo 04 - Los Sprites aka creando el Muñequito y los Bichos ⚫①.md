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
created: 2025-06-09T14:52:48.676Z
modified: 2025-06-11T16:28:13.849Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 04 - Los Sprites aka creando el Muñequito y los Bichos ⚫①

![El Sprite del prota de JBA](PublicBrain/_resources/075d786a132e2fa4dc5a7495aee94f97_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 03 - Nuestra primera pantalla  ⚫①|<< Anterior]]  | [[Tutorial de AGD 2018 Capitulo 05 - Animando sprites ⚫①|Siguiente >>]]


Una vez tenemos [[Tutorial de AGD 2018 Capitulo 03 - Nuestra primera pantalla  ⚫①|los tiles y al menos una pantalla de las entregas anteriores de este Tutorial de AGD en español]], y antes de profundizar en los detalles de la configuración de suelos y paredes, o los mapas, vamos a completar los elementos básicos que necesitaremos para crear un juego: nuestro protagonista y los enemigos a los que se enfrentará, tpdp ello, usando Sprites.
## Antes de nada, un poco de contexto.

Aunque mi objetivo principal es enseñar com hacer un juego con AGD y que a partir de ahi cada cual pueda marcar su camino, como vengo haciendo quiero antes, dar un poco de contexto sobre sprites.

Mos haremos conscientes de las limitaciones de las maquinas de la época de los 8 bits, lo que supone todo un reto a nivel artístico.

 ## Marty... ¿no tendré que llamarte gallina no? ;))

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/d4zOOv0OrVk?si=_KY8scoc9Bt9C7SV" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

[En el caso de Spectrum tenemos un color para la tinta y otro para el fondo a elegir entre 7 por cada area de 8x8 pixels pudiendo usar o no brillo 🌐🟡③](https://es.wikipedia.org/wiki/Modos_gr%C3%A1ficos_del_ZX_Spectrum) de forma que (salvo del negro) tenemos dos versiones de cada color.

Eso si no podemos hacer que la tinta tenga brillo y el fondo no, todo con brillo o sin brillo.

Al margen de las especifiadades de color de Spectrum, así como las especifidades del color de los sprites en AGD que veremos mas adelante, abramos boca con estos dos videos que nos dan una gran perspectiva sobre la materia.

Hay subtítulos en español para los que no domineis el ingles.

```pre 
Para temas de desarrollo el ingles es básico.
```
**<iframe width="100%" height="480" src="https://www.youtube.com/embed/Tfh0ytz8S0k?si=QYgJ0CDtrZjXIzuR" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/_rsycfDliZU?si=iYl1fo3mP-v6u9w9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>****

## Y en AGD … ¿Como va esto de los Sprites

Lo primero es pulsar S desde el menú principal.

Accederemos al editor de Sprites donde podremos generar nuestras creacioes.

Las dimensiones son definidas a través de la opción i "Miscelánea", [[MOS Games - The Big Javis Adventure - ZX Spectrum - 2017|en el caso de JBA he usado Sprites de 16x16]].

![Nuestro prota de JBA en el editor de sprites](PublicBrain/_resources/f6581817fe446293c189d2b5f1072001_MD5.jpeg)

  El interfaz es bastante sencillo, un cuadro enorme en la parte superior izquierda que nos permite editar el sprite al gusto, un indicador del numero de sprite en que nos encontramos y el frame que estamos editando (los sprites pueden tener varios frames de animación.

### ¿En qué consiste esto de los "frames de animación"?.

Siempre que observamos un "muñequito" en la pantalla, vemos que se mueve, no es - habitualmente - una imagen estática, para lograr este efecto, se dibuja al personaje varias veces con la postura ligeramente cambiada, como en los dibujos animados. Al mostrar estos dibujos en secuencia a una velocidad apropiada, percibiremos que "se mueve". Este pequeño video lo explica muy bien:

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/G9m1Aku_bPk?si=A3HuYSARSsXQOpsN" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

## Manejando el edito de sprites

>Ahora creo tenemos claro el contexto general.

Es el momento de indicar las teclas que debemos usar en esta pantalla.

Crearemos nuestros muñequitos y bichos, el movimiento básico se realiza con cursores y space para cambiar el pixel donde se sitúa el cursor:

```pre
TECLAS
======= -----------------------------------------------
- X = Insertar Sprite
- D = Borrar Sprite
- C = Borrar el contenido del Sprite
- Cursores = Movemos el puntero por la rejilla del Sprite
- Space or 0 = Cambia el pixel actual (activo/inactivo)
- M = Copia el sprite al portapapeles
- K = Pega el sprite dede el portapapeles
- H = gira horizontalmente el sprite
- V = gira verticalmente el sprite
- N = Moverse al sprite siguiente
- P = Moverse al sprite siguiente
- I = insertar frame
- R = borrar frame
- F = Ir al siguiente frame
- ENTER = Volver al menú principal
```
### Copiar bloques de un Load Screen

El editor, según el manual de la version 4.6, tiene una pantalla en la que podemos cargar ficheros de tipo screen$, usando la tecla L. Una vez en esa pantalla, se puede mover un cursor de 16x16 pixels y copiar porciones de ella al portapapeles (usando space) desde el que luego podremos pegar usando la letra K.

```pre
TECLAS
======= -----------------------------------------------
- L = carga una pantalla al editor para copiar trozos
- G = vuelve a la pantalla cargada para copiar otro trozo
- Space en la pantalla cargada = Copia el trozo activo
- Cursores en la pantalla cargada = Mover Cursor de Copia.
```
Mas alla de esto, el funcionamiento es muy similar a los bloques, solo que aqui cada "Sprite" puede contener mas de un frame de animación , ya veremos como se usan las animaciones pero podéis practicar creando al protagonista (o vuestro propio "muñequito" con al menos 4 frames de animación, mirando a izquierda y derecha.

>No os limiteis a copiar sin mas los sprites, y dadles vuestro propio toque una vez que tengas claros los fundamentos.


Adicionalmente, y como ejercicio para afinar vuestro desempeño podeis tratar de replicar (y animar) los gráficos que sugiero a continuación.

```
¡Se me olvidaba! podeis usar la tecla F dentro del editor para ver en sucesión los frames y hacer preview de vuestra animación y asi corregirla... ¡antes de mandar vuestra creación a Dinamic!
```

### Algunos ejemplos mas


![Sprite de enemigo en una nave voladora en el edito](PublicBrain/_resources/c523a9ddf4680d84637f7c3f5c2c1a7e_MD5.jpeg)

![Sprite de la llama en el editor](PublicBrain/_resources/b3bbeaa2d42affc8f37f1ebf347588b8_MD5.jpeg)

![Sprite de los lemmings estilo monty pyton en el editor](PublicBrain/_resources/6c2f0adabef491261f303463d87384a0_MD5.jpeg)

En los próximos capítulos, os mostrare mis pruebas con la funcionalidad de copiar bloques desde pantallas de carga, y empezaremos a situar los muñequitos en la pantalla que creamos en capítulos anteriores, esto nos dará pie para ampliar los conocimientos de forma práctica.

## ¿Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si has lllegado aqui tras una abducción y quieres entender que es esto, pasa a la página 1]]
* [[Tutorial de AGD 2018 Capitulo 04 - Los Sprites aka creando el Muñequito y los Bichos ⚫①|Si tienes que recuperar el resuello, espera aqui, en la página 4]]
* Si estás ebrio de gozo y quieres continuar, haz una tirada de equilibrio mientras el mesero trae otro barril de cerveza.

## Referencias Bibliográficas

* [How "oldschool" graphics worked Part 1 - Commodore and Nintendo - The 8 Bit Guy  🌐🟡③](https://www.youtube.com/watch?v=Tfh0ytz8S0k&list=PLiKMC8C3e0b3mlLFaiCM4GgQC9uWD5lc2&index=10)
* [How "oldschool" graphics worked Part 2 - Apple and Atari - The 8 Bit Guy  🌐🟡③](https://www.youtube.com/watch?v=_rsycfDliZU&list=PLiKMC8C3e0b3mlLFaiCM4GgQC9uWD5lc2&index=11)
* [Cómo crear un dibujo animado - La Información - Practicopedia  🌐🟡③](https://www.youtube.com/watch?v=G9m1Aku_bPk&list=PLiKMC8C3e0b3mlLFaiCM4GgQC9uWD5lc2&index=12)



![[Plantilla - 1MT#One More Thing]]