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
created: 2025-08-08T22:34:30.911Z
modified: 2025-08-10T15:42:32.968Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 25 - Buscando como poner música en AGD usando el chip AY ⚫①

![Nos hacemos unos vortex?](PublicBrain/_resources/94d9620fb019da3aca9f15ac8accb106_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 24 - Efectos de Sonido con el chip AY ⚫①|<< Anterior]] |  [[Tutorial de AGD 2018 Capítulo 26 - Edición avanzada en AGD con la herramienta Perilla de Sergio thEpOpE  ⚫①|Siguiente >>]]

Ha llegado, el momento, hoy comenzamos el proceso de incorporar música ingame a nuestro juego de AGD. Lo primero, preguntar a los que saben, y por ahora, el tutorial más claro que he encontrado es este:

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/6DCqRXNZGGw?si=mtpzQbZzzGwkB3hC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

Es largo, y aunque en esencia es sencillo, en la práctica es laborioso. Por tanto me voy a tomar con calma el mostrar como y lo haré paso a paso, que no tenemos prisa.

Hoy, planteare la hoja de ruta y semana a semana iré mostrando cada paso con detalle suficiente. Si la realidad me supera, intercalaré alguna cuestión como las escaleras en AGD y esas cuestiones que aún no he tratado.

## La hoja de ruta

En esencia, poner musica a nuestro juego, se divide en las siguientes fases:

1. Componer nuestra música con Vortex Tracker
2. Exportar la música y el reproductor e incorporarlos al tap.
3. Incluir la rutina que controlará la ejecución "simultánea" de música y juego.
4. Modificar el cargador basic para cargar los nuevos bloques.
5. Modificar AGD para que llame a la rutina de ejecución simultánea en el momento apropiado.
6. Me acabo de parecer mucho a la parodia de bricomanía en plan "Construyendo tu propia catedral gótica" xD

## Instalando Vortex Tracker

Empecemos con el paso número uno, en mi caso he logrado ejecutar [Vortex Tracker 🌐🟡③](https://bulba.untergrund.net/vortex_e.htm) tras [descargar esta versión del tracker 🌐🟡③](https://bulba.untergrund.net/VT1.0beta19Plus.7z), usando Wine en mi Mac. Si tienes Windows no deberías tener problemas, siempre que puedas ejecutar programas de 32 bits.

Una vez arrancado, supongo que os pasará que bien no habéis tocado nunca el programa, bien que lo último que hicisteis con este tipo de programas, como es mi caso, fué con Impulse Tracker en MS-DOS, por lo que tengo localizado este [manual del tracker para poder iniciarme en su manejo 🌐🟡③](http://www.culturachip.org/doku.php?id=tuto_vortex)

Como veis no es complejo, pero nos llevará algo de trabajo dominar la técnica, así pues, ¡vamos a ello!

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si vas piripi, ve balbuceando fiòifofdoffofoo! a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 23 - Secuencia de victoria ⚫①|Si has tenido que bajarte del tiovivo para que no te atropelle la cuádriga y el coche de bomberos, ve a que te curen en la página 23]]
* [[Tutorial de AGD 2018 Capítulo 24 - Efectos de Sonido con el chip AY ⚫①|Si esta semana tienes la práctica del cole con flauta dulce, ve a practicar a la página 24]]
* [[Tutorial de AGD 2018 Capítulo 26 - Edición avanzada en AGD con la herramienta Perilla de Sergio thEpOpE  ⚫①|En caso de que hayas venido, pero no hayas llegado, aguanta una mica y pasa a la página 26]]

![[Plantilla - 1MT#One More Thing]]