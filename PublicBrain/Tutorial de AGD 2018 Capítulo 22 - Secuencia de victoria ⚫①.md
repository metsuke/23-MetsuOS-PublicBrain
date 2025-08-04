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
created: 2025-08-04T13:07:01.307Z
modified: 2025-08-04T16:27:30.828Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 22 - Secuencia de victoria ⚫①

![Secuencia de victoria](PublicBrain/_resources/61d3f353b0e2b7406500962e60ab2b11_MD5.jpg)

 * [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 21 - Menú de Presentación ⚫①|<< Anterior]] | Siguiente >>

En el capítulo anterior vimos [[Tutorial de AGD 2018 Capítulo 19 - Ciclo de vida ⚫①|el ciclo de vida]], y la [[Tutorial de AGD 2018 Capítulo 21 - Menú de Presentación ⚫①|secuencia de menú inicial]], hoy veremos los fundamentos de la secuencia de victoria.

## Que hacer cuando nuestro jugador gana la partida

En primer lugar, ponernos muy contentos, con el nivel de oferta actual en el mundo del videojuego en general y clásico en particular. que alguien se tome la molestia de jugar nuestro juego hasta el final es muy de agradecer.

**<iframe width="100%" height="480" src="https://www.youtube.com/embed/ROsZnPPf1pE?si=ljlqS-UhUiEvb8lf" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>**

Pero claro, en AGD hemos de hacer algo cuando la condición de victoria se cumple, gestionando el evento 
"Completed Game"

## ¡Hemos ganao los del equipo colorao!

Jamás pensé que podría poner esto en un post jaja, pero justamente viene a colación, cuando nuestro valioso jugador completa el juego, es de recibo que le demos, como mínimo, la enhorabuena.

Antaño en demasiadas ocasiones el final se limitaba a un "Enhorabuena has completado el juego". Esto es algo que personalmente no comparto, tras el esfuerzo de completarlo , que menos que currarselo un poquito ¿no?.

## Secuencia de Completed Game

Para ilustrar esto, voy a describir como lo hago en [[MOS Games - The Big Javis Adventure - ZX Spectrum - 2017|JBA]]. En primer lugar, la detección de la victoria se da en el Evento de Sprite Type 0, en el momento de recoger un objeto comprobamos si hemos llegado a 60 y si es así ejecutamos ENDGAME.

En la rutina, a más de dar la enhorabuena, aprovecho para mostrar varias pantallas realizadas a base de bloques, es un consumo de memoria está claro, pero al usar bloques podemos lograr un buen equilibrio entre espectacularidad y ahorro.</p>

En esencia la secuencia de pantallas muestra el despegue del Cohete [ZX-UNO 🌐🟡③](http://www.zxuno.com/forum/) que llevará a nuestro querido [Speccy Master Spectrumero 🌐🟡③](https://www.youtube.com/@ElSpectrumeroJaviOrtiz) al espacio en busca del malvado Vegatrón para darle una buena turra.

Logro mostrar esta "historieta" con un par de pantallas pausa mediante pulsación de tecla en medio y una serie de sonidos que celebran la victoria y simulan el despegue. Os dejo investigar como logro los efectos sonoros, más adelante lo contare :)

Una vez finalizadas esas pantallas y tras la pulsación de tecla correspondiente, aparecen los créditos, sobre una tercera pantalla (que encabeza este artículo como ejemplo),

Tras mostrar esta última pantalla, se simulan unos fuegos artificiales a nivel sonoro y se espera una tecla para volver al menú principal.

Puede que, en los tiempos que corren, pueda ser un final parco, pero creanme que dentro del contexto histórico del ZX Spectrum, se puede considerar hasta un "exceso".

No tiene nada más, podéis investigar como hago los sonidos y gestionar el silenciado del sonido entre pantallas, para ir abriendo boca. ¡Nos vemos en el próximo capítulo!

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no sabes como estaba la plaza, averígualo en la página 1]]
* [[Tutorial de AGD 2018 Capítulo 21 - Menú de Presentación ⚫①|Si tienes curiosidad por conocer más a quien se acaban de presentar en plaza, pasa a la página 21]]
* [[Tutorial de AGD 2018 Capítulo 22 - Secuencia de victoria ⚫①|Si la plaza estaba abarrotá, pasa a la página 22]]
* Si sabes cantar ¡22!, ¡22, 22 , 22! correctamente, estás preparado para conocer al Duo Sacapuntas, en la página 23


![[Plantilla - 1MT#One More Thing]]