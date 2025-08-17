---
iaStatus: 8
iaStatus_Model: ""
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-08-17T19:46:12.748Z
modified: 2025-08-17T19:57:03.490Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 1
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 30 - Estructura de Memoria de AGD ⚫①

![Estructura Memoria GD](PublicBrain/_resources/d1559d6541fd62e84303a5a9c1ba64c5_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 29 - El contexto lo es todo ⚫①|<< Anterior]] |  Siguiente >>

Vamos a incorporar música de prueba a JBA con Vortex Tracker, y en el proceso de estudio, me he encontrado con la necesidad de mover bloques de datos en la memoria de nuestro spectrum. 

Para ello, nada mejor que tener claro como almacena los datos AGD para así ver donde podemos encajarlos.

Partamos de esta fantastica explicación de thE pOpE:

<iframe width="100%" height="480" src="https://www.youtube.com/embed/7Xl6ty1k_9c?si=-zW_uVv5X8azespL" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
## Bloques de Memoria AGD

Tratemos de crear una tabla con la información dispoinible gracias a thE pOpE, y, en el caso de la información variable, en que direcciones de memoria deben consultarse, a ver si somo capaces :)

|Bloque|Desde|Hasta|Notas|
|---|---|---|---|
|Pantalla de Carga|$4000 (16384 DEC)|$5B00 (23296 DEC)|La memoria de pantalla ocupa 6912 Bytes que comienzan en –|

System: It looks like the response was cut off. Below is the complete Markdown table for Obsidian, ensuring it can be easily copied and pasted, maintaining the original content from the HTML table you provided.

|Bloque|Desde|Hasta|Notas|
|---|---|---|---|
|Pantalla de Carga|$4000 (16384 DEC)|$5B00 (23296 DEC)|La memoria de pantalla ocupa 6912 Bytes que comienzan en 16384 DEC.|
|Espacio Libre|$5B01 (23297 DEC)|$75B8 (30136 DEC)|Quizá tengas que ajustar el límite superior si tu bloque de juego en el tap tiene un tamaño diferente, pero en JBA parece ser así, algo más de 6,5Kb|
|Editor AGD|$75B9 (30137 DEC)|$7CFF (31999 DEC)|Depende del escenario está o no presente / Direcciones establecidas observando el cargador de AGD y el límite inferior del Engine, para JBA|
|Engine AGD|$7D00 (32000 DEC)|||
|Datos Juego||||
|Código AGD|||Una vez detectado donde comienza y donde acaba, podremos sobrescribir este área.|
|Código Z80||$EED9 (61145 DEC)|Dirección Hasta obtenida examinando tamaño bloque de datos de [JBA 1.1](https://www.metsuke.com/sobre-mi/videojuegos/the-big-javis-adventure-2017/). Podría ser diferente en cada juego.|
|Espacio Libre|$EEDA (61146 DEC)|$FCFF (64767 DEC)|Si los cálculos son correctos, esto nos deja con algo más de 3500 Bytes|
|Mapa de Durezas|$FD00 (64768 DEC)||Si hay hueco por encima de esto, no lo sé aún, al desconocer cómo funciona dicho mapa de durezas.|
**Estructura en memoria de un juego AGD v0.1**

Parece que tendré que trabajar más esta cuestión, no parece haber información disponible en la red, por lo que he deducido las que he podido, según avancen mis investigaciones iré actualizando este artículo.

Si tienes información al respecto por favor, ¡házmela llegar!

Esto por un lado me anima a investigar, por otro, a usar esa investigación para construir MGD (Metsuke Game Designer), basado en MPL, ¡poco a poco!

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si crees que es serio este cementereio ve a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 28 - Test final y creación del .tap ⚫①|Si no tienes claro lo del rancio abolengo, pasa a la página 28]]
* [[Tutorial de AGD 2018 Capítulo 29 - El contexto lo es todo ⚫①|Si te gusta que lo pasen muy bien entre flores de colores, pasa a la página 29]]
* Si el cielo no puede esperar, pasa a la página 31

![[Plantilla - 1MT#One More Thing]]