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
created: 2025-08-18T15:15:20.828Z
modified: 2025-08-18T20:17:10.295Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 31 - Ejemplo básico jugando con tipos y animaciones ⚫①

![Ejemplo adicional](PublicBrain/_resources/c64bc1fa1a4455f4cd78d2a079046b3e_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 30 - Estructura de Memoria de AGD ⚫①|<< Anterior]] |  Siguiente >>

Hace pocas fechas, comentaba con algunos desarrolladores la posibilidad de gestionar el bucle de animación haciendo que se ejecutara una vez, así como jugar con tipos de sprites.

Para ejemplificar esto, he construido [este ejemplo que comparto aquí con todos, para su descarga](https://metsuke.com/assets/dnld/AGD_EsponjasSorprendidas.z80).

Es un ejemplo básico que juega con los tipos 1 y 2, los "Bob Esponja" son de tipo 1 y van libres rebotando en las paredes, al chocar con una, se quedan "pegados" momentaneamente pasando a tipo 2 (momneto en el cual se ejecuta la animación para que se queden sorprendidos una sola vez).

Tras un tiempo pequeño aleatorio, vuelven a modo 1 y siguen viaje. Cuando chocan con un tipo 2 se quedan "enganchados" gracias a una sencilla funcionalidad.

¿Serías capaz de hacer que cuando dos tipos 1 se encuentren choquen entre si y cambien de dirección aleatoriamente sin coincidir? te animo a que nos compartas tu versión.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si crees que es serio este cementereio ve a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 28 - Test final y creación del .tap ⚫①|Si no tienes claro lo del rancio abolengo, pasa a la página 28]]
* [[Tutorial de AGD 2018 Capítulo 29 - El contexto lo es todo ⚫①|Si te gusta que lo pasen muy bien entre flores de colores, pasa a la página 29]]
* [[Tutorial de AGD 2018 Capítulo 31 - Ejemplo básico jugando con tipos y animaciones ⚫①|Si el cielo no puede esperar, pasa a la página 31]]

![[Plantilla - 1MT#One More Thing]]