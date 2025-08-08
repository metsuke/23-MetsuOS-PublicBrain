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
created: 2025-08-08T19:08:51.425Z
modified: 2025-08-08T19:11:15.842Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 1
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 24 - Efectos de Sonido con el chip AY ⚫①

![Editor de sonidos AY de AGD](PublicBrain/_resources/f4182946b622c16a7af056201cfb26fa_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 23 - Efectos de sonido con Beep ⚫①|<< Anterior]] | Siguiente >>

En el anterior capítulo hablamos de [[Tutorial de AGD 2018 Capítulo 23 - Secuencia de victoria ⚫①|los efectos de sonido con BEEP]], hoy comentaremos como manejar la opcion SOUNDS que usa el chip AY.

Lo primero, como siempre, entramos con la opción F, y se vuelve al menú, como siempre, con [la tecla INTRO 🌐](https://www.instagram.com/p/CC7RdRGo1Xj/?utm_source=ig_web_copy_link), verán una pantalla que se parece a un tracker mod, pero adaptado al estilo AGD

Veamos pues, como es tradicional, las teclas con que se maneja esta función:

```pre
ATAJOS DE TECLADO
==================

* H = Escuchar el sonido en pantalla
* N = Sonido siguiente
* P = Sonido Anterior
* X = Crear un nuevo sonido
* D = Borrar el sonido actual

Cursores = moverse por las opciones

* 1 = Incrementar la opción seleccionada
* 2 = Decrementar la opción seleccionada
* 3 = Incrementa el tono en bloques de 50
* 4 = Decrementa el tono en bloques de 50

Space = Desactivar el sonido o tono seleccionado
```
El funcionamiento es, en esencia muy sencillo, vemos una lista de 10 elementos con volume, noise y tone. Funciona como un tracker, al ejecutar se harán sonar en secuencia los 10 elementos, y la unión de todos ellos dará como resultado un sonido concreto.

Iremos jugando con las configuraciones y usaremos H para escuchar el resultado, para crear nuestro sonido. Importante, además de jugar con las opciones, quizá tener claro para qué creamos un sonido, y evitar llenar la memoria de sonidos que luego no se usen, no en vano cada sonido ocupa 41 bytes.

En mi caso hice los sonidos por ensayo y error, pues - por ahora - no tengo formación suficiente para hacer cosas a tiro hecho, puedes [[Tutorial de AGD 2018 Capitulo 12 - Cargar juegos de AGD desde cinta ⚫①|ver como están hechos los del JBA]] por ti mismo y extrapolar desde ahí.

A la hora de utilizarlos en el juego, usaremos SOUND y su número donde corresponda para hacerlo sonar y SILENCE para parar el sonido en curso.

## Usando la Perilla para jugar con los efectos de sonido

Gracias a [Sergio "thEpOpE" 🌐🟡③](https://www.youtube.com/@thEpOpESergio), tenemos también la opción de utilizar la perilla para extraer los sonidos, editarlos e incluso crear nuevos para luego introducirlos nuevamente en nuestro juego AGD.

En este video (minuto 14 en adelante) de su canal nos lo cuenta en detalle:

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/WtmVoDtXTPE?si=CX2JthaBkAD_8oQ8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

Quiero crear músicas para JBA así que toca estudiar, [por ahora empezaré por este hilo 🌐🟡③](https://www.va-de-retro.com/foros/viewtopic.php?t=1109), e iré avanzando, espero poder contaros lo básico de cómo hacerlo la próxima semana (mandadme ánimos, los voy a necesitar xD)

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?


* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si vas a hacer pipi, ve cantando pipipi pipipi! a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 23 - Secuencia de victoria ⚫①|Si por lo que sea aún te pitan los oidos, pita pita pita del hasta la página 23]]
* [[Tutorial de AGD 2018 Capítulo 24 - Efectos de Sonido con el chip AY ⚫①|Si vas de paseo pipipi, ve pitando a la página 24]]
* En caso contrario, no vayas a la página 25, porque aún no existe.

![[Plantilla - 1MT#One More Thing]]