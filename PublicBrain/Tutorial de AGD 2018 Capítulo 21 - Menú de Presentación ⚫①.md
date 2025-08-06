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
created: 2025-08-02T21:06:02.884Z
modified: 2025-08-06T22:53:46.611Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 21 - Menú de Presentación ⚫①

![Trabajando en la pantalla de menu](PublicBrain/_resources/9defbc9443997d93e700e8e640aac569_MD5.jpg)
 
* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 20 - Creando Objetos ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capítulo 22 - Secuencia de victoria ⚫①|Siguiente >>]]

Hoy comentaremos en lenguaje sencillo la pantalla de presentación.

Como ya vimos en [[Tutorial de AGD 2018 Capítulo 19 - Ciclo de vida ⚫①|el capítulo dedicado al ciclo de vida]], el cometido del menú de presentación es sencillamente introducirnos al juego y ofrecernos las opciones de control, una vez seleccionado el control comenzará la partida.

## Pero ¿Qué se hace exactamente a efectos de código?

Bien , lo primero, sirva decir que la acción se desarrolla en el evento \"Intro / Menú\", aunque puedes inventar tu propio método, yo hago lo siguiente:

1. Ejecuto SILENCE para parar todos los sonidos del juego.
2. A lo largo del proceso de menú ejecutar sonidos aquí y allá para dar variedad y robustez a algo por otra parte relativamente anodino como un menú.
3. Ejecuto una secuencia CLS, luego asigno la variable SCREEN a una en que he preparado un bonito fondo para el menú, para a continuación ejecutar CLS y REDRAW para completar un efecto básico de recarga (aunque bastante efectivo visualmente).
4. Usando LINE, COLUMN, COLOUR y MESSAGE dibujo el nombre del juego, otros mensajes como el copyright y las diferentes opciones del menú, a saber: 1. KEYBOARD, 2. KEMPTSTON, 3. SINCLAIR que son las que reconoce la instrucción del menú de control de AGD y una cuarta en la que suelo hacer algun chiste o mandar algún mensaje.
5. Finalmente ejecuto CONTROLMENU que espera a la pulsación de una tecla y asigna el control según lo indicado por el usuario para finalmente redirigir el flujo de ejecución para que comience el juego.

Como veis algo relativamente sencillo de planificar.

## Precaución

Este es un código relativamente simple, pero que llega a ser muy farrogoso, ahorra memoria donde puedas y sobre todo mantenlo muy limpio para evitar complicarlo mas alla de lo necesario.

**¡MUY IMPORTANTE!** En diversas ocasiones he tratado de usar bucles REPEAT dentro del evento Intro/Menú y en todas ellas el resultado ha sido desastroso, no se porque , pero cuando introduzco esta instrucción, el caracter space empieza a pintarse como uno de los bloques de los mapas. He optado por no usar REPEAT en este código, aún a costa de perder algunos bytes.

En el próximo capítulo os comentaré el tema de los TEXTOS de los que se alimenta la instrucción MESSAGE. 

> Consejo: no olvidéis hacer backup a cada paso si decidís explorar TEXTOS por vuestra cuenta, es una opción muy inestable.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no te has presentado, reagrúpate en la página 1]]
* [[Tutorial de AGD 2018 Capítulo 21 - Menú de Presentación ⚫①|Si tienes curiosidad por conocer más a quien te acaban de presentar, pasa a la página 21]]
* [[Tutorial de AGD 2018 Capítulo 22 - Secuencia de victoria ⚫①|Si tu te has presentado yo me he presentado y ha sido una buena conversación, pasa a la página 22]]


![[Plantilla - 1MT#One More Thing]]