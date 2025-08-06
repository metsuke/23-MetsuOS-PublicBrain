---
iaStatus: 8
iaStatus_Model: Grok-3, Raul Carrillo aka metsuke
iaStatus_Generado: "H"
iaStatus_Supervisado: "-"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-08-06T22:51:52.675Z
modified: 2025-08-06T22:53:58.013Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 1
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 23 - Efectos de sonido con Beep ⚫①

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 22 - Secuencia de victoria ⚫①|<< Anterior]] | Siguiente >>

AGD nos brinda dos modos básicos de emitir sonido, en el capítulo de hoy centramos nuestra atención en [[Tutorial de AGD 2018 Capitulo 10 - Referencia del Lenguaje ⚫①|el comando BEEP]]

A diferencia del BEEP de BASIC en ZX Spectrum, el comando en AGD solo recibe un parámetro, la duración, a mayor número, mayor duración. 

El tono empieza bajo y se va incrementando automáticamente a lo largo del tiempo.

Es un método limitado, pero relativamente efectivo a la hora de realizar efectos de sonido de forma ágil y efectiva. 

Para ilustrar el método, voy a mostrar como he creado algunos de los efectos en «[[MOS Games - The Big Javis Adventure - ZX Spectrum - 2017|The Big Javi's Adventure]]»:

## Pasos del Protagonista

Este es uno de los ejemplos más típicos, en uno de los frames de la animación del personaje, cuando este \"toca el suelo con el pie\", ejecutamos un pequeño BEEP del modo siguiente (muestro un segmento del movimiento a la derecha, al contrario es idéntico).

```basic
(...)
ANIMATE
IF FRAME = 2
  BEEP 3
ENDIF
(...)
```

De este modo está realizado el tiquitiqui característico del prota.

## Sonido de Correr

El efecto de correr se consigue manteniendo pulsadas dos teclas, como por ejemplo Q y O, esto ejecuta el BEEP del ejemplo anterior dos veces en cada bucle del juego, lo que aporta el efecto de correr. Mismo código, doble uso.

## Impulso previo al salto

Hablo de impulso previo al salto y no de salto en si mismo, debido a que el efecto es compuesto, el impulso inicial, hecho con BEEP que os comentaré hoy y el \"Toing\" realizado con AY y que se usan en secuencia para generar la ilusión de un sonido compuesto.

El impulso se logra usando la siguiente secuencia:

```basic
(...)
BEEP 3
SOUND 1
(...)
```

## Recoger Objeto

Este es un efecto algo más \"elaborado\", cuando recogemos un objeto ejecutamos un bucle basado en el número de vidas restantes, por cada iteración se asignan 100 puntos y finalmente se ejecuta un sonido adicional mediante AY.

```basic
(...)
GET OBJ
REPEAT LIVES
  SCORE 100
  (...)
  BEEP 50
  DELAY 5
ENDREPEAT
SOUND 2
(...)
```

## La Eterna Gota

En el caso de la gota, su sonido al caer es una secuencia de BEEPs que suena al tocar el suelo:

```basic
(...)
BEEP 8
BEEP 10
BEEP 20
(...)
```

## Muerte Asesinato de John Spartan

En este caso el efecto de sonido que se ejecuta cuando te matan una vida, es otra secuencia de BEEPs pero descendente y cuyos elementos duran bastante:

```basic
(...)
DELAY 10
BEEP 205
BEEP 190
BEEP 176
DELAY 5
(...)
```

Creo que no me dejo ninguno, estoy seguro que explorando más a fondo este comando se pueden lograr cosas interesantes, por ahora esto es lo que sé sobre la materia :)

En el próximo capítulo exploraré la parte del Sonido AY que se realiza mediante SOUND desde el interfaz oficial, para posteriormente explorar la música tracker integrada en el juego mediante llamadas CM. Mientras, ya sabéis, practicad, practicad, practicad.
## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no sabes si Beep Naranja o Beep Cristal, averígualo en la página 1]]
* [[Tutorial de AGD 2018 Capítulo 22 - Secuencia de victoria ⚫①|Si en tu cabeza suena Beep Beep Beeep Beeb Beep y estas pensando en Carnaval, pasa a la página 22]]
* Si no te importa, porque llevas torta, ve con el coche de papa a la página 24

![[Plantilla - 1MT#One More Thing]]
