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
created: 2025-06-20T21:52:33.909Z
modified: 2025-06-20T21:53:26.753Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 1
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 08 - Mover a nuestro protagonista por la pantalla ⚫①

![La iconica pantalla de la cascada](PublicBrain/_resources/b8997349c974172658a41b4545387749_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 07 - Editor del Mapa ⚫①|<< Anterior]] | Siguiente >>

En este capítulo abordamos el manejo de nuestro personaje protagonista con AGD, empezaremos por el ejemplo más simple para, en posteriores capítulos afinar cada uno de los aspectos necesarios, desde la configuración de los bloques hasta la selección del modo de control.

Doy por hecho que habéis [[Tutorial de AGD 2018 Capitulo 04 - Los Sprites aka creando el Muñequito y los Bichos ⚫①|creado al menos un sprite]] y [[Tutorial de AGD 2018 Capitulo 05 - Animando sprites ⚫①|lo habéis animado]] siguiendo el tutorial. Usaremos todas las opciones por defecto para llegar lo antes posible a mover uno de ellos en pantalla.

## Paso 1: Plantilla de Código

En capítulos posteriores aprenderemos más a fondo lo que podemos lograr a través de código, pero por ahora usaremos una de las plantillas por defecto que nos aporta AGD.

Entramos desde el menú principal en Eventos (tecla E), desde ahí a la primera opción (Player Control type 0), y pulsamos Espacio (space). Como no tendremos código escrito ahí, AGD nos ofrecerá varias plantillas y asignaremos la llamada "tipo manic miner", esto nos creará un código base que permite controlar al protagonista, lo tendremos que afinar más adelante, pero nos servirá para comenzar y analizar cómo funciona en el próximo capítulo.

>Pulsaremos CTRL+A para guardar y volver al menú de evenos y de ahi volvemos al menú principal.

## Paso 2: E hice chof cataplof

Desde el menú principal, pulsamos X para ejecutar el juego, por defecto aparecemos en medio de una pantalla probablemente en negro, o puede que la que hayáis creado, pero el protagonista de nuestro juego simplemente caerá varias veces muriendo y acabará la partida.

¿Que ha pasado? bien, básicamente que el sistema de código Manic Miner implementa una física y si caemos desde muy alto morimos, esto unido a que el personaje por defecto aparece en el centro de la pantalla... pues eso, puré instantáneo de Sprite xD.

Solucionaremos esto usando por primera vez la opción Sprite Positions (N) desde el menú principal , como no hemos creado apenas nada, al entrar veremos nuestro protagonista en el centro como cuadro parpadeante, con los cursores lo bajaremos a ras de "suelo" (borde inferior de la pantalla) y pulsaremos intro.


![Una de las pantallas de la caverna en JBA](PublicBrain/_resources/0deb0b7ab3e2c4c0f4e5a28e861e92d9_MD5.jpeg)
  
## Paso 3: Movimiento Básico

Ahora si, pulsamos de nuevo X para iniciar el juego y aparecemos en la parte inferior de la pantalla, esta vez sin morir. Usaremos las teclas 9 y 0 para movernos a izquierda y derecha, para saltar usaremos la tecla 2.

E voilá, nuestro muñeco, aun de forma rudimentaria y con un montón de cosas que aún no entendemos se estará moviendo por la pantalla, hay aspectos variados como el de que no "choca" con el escenario, que por ahora no sabemos controlar, pero os insto a que investigueis como funciona el codigo de la plantilla (aunque lo rompáis, siempre se puede borrar y volver a asignarlo), esto os ayudará a evolucionar mucho más que unicamente siguiendo lo pasos sin más.

Detalles hay mil que se pueden mejorar, desde las colisiones al salto, pasando por la animación en cuanto a fluidez y orientación (os daréis cuenta de que el muñequito siempre mira al mismo lado). Todos estos detalles los iremos abordando, pero en el siguiente haré una disección del código de esta plantilla porque nos permitirá aprender un montón de como funciona AGD y así luego poder idear nuestras propias mecánicas.

Mientras llega la próxima entrega, recordad "Practicar, practicar, practicar!"

## ¿Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si hs aterrizado aquí directamente desde Ventormenta sin encargarte de Hogger, pasa a la página 1]]
* [[Tutorial de AGD 2018 Capitulo 08 - Mover a nuestro protagonista por la pantalla ⚫①|Si quedaste aturdido al caer desde el por tal de Theramore, descansa un rato en la página 8]]
* Si quieres abrir un portal a Theramore a Hogger y hacerlo desaparecer de una vez por todas, ve al instructor de portales mientras informamos al Mossad de lo que tienes pensado.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

![[Plantilla - 1MT#One More Thing]]