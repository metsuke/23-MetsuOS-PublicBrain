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
created: 2025-07-12T20:02:55.651Z
modified: 2025-07-18T20:10:16.560Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 13 - Manual de uso del Editor de Código ⚫①

![Aprendiendo a manejar el editor de código](PublicBrain/_resources/41d7db1408ace939af5b63f34e9ed78a_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 12 - Cargar juegos de AGD desde cinta ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capítulo 14 - Conectando panallas entre si  ⚫①|Siguiente >>]]

Hoy les traigo uno de esos capítulos que pueden parecer superfluos, pero que son todo lo contrario. Vamos a comentar algunas cuestiones y trucos para trabajar con el editor de código de AGD.

Seguramente para los más experimentados esta información esté de más, pero no es raro encontrar personas que se enfrentan por primera vez a las combinaiones de teclas de speccy dentro de un emulador en otro sistema operativo y que se vuelven locos al tratar de trabajar el código de su juego. 

Empiezo por el final, incluyendo las combinaciones de teclas que el propio autor de AGD nos aporta en su manual:

```pre
Teclas del Editor de Código
============================
* SYM+Y Cortar Línea
* SYM+U Pegar Linea
* SYM+Q Inicio
* SYM+E Fin
* CAPS+2 Bloqueo Mayúsculas On/Off
* CAPS+3 Borrar carácter seleccionado.
* CAPS+4 Cambiar entre Insertar y Sobreescribir.
* SYM+CAPS Modo Extendido (E) On/Off
* SYM+A Compilar evento y volver al menú de eventos.
```
## Navegando entre eventos

Vemos primero la rutina de \"entrada y salida\" desde el menú principal al codigo y entre los eventos, sirva decir que os recomiendo cargar una instancia nueva de AGD para practicar sin riesgo.

Lo primero, *acceder al menú de eventos* desde el menú principal, tan simple como pulsar la tecla *E*. Para volver al menú principal desde los eventos, tan sencillo como pulsar *INTRO*.

Para recorrer el menú de eventos, se usan los *CURSORES*, para entrar a ver y/o editar el código de cualquiera de ellos, usamos *SPACE*.

Una vez dentro del propio editor, volvemos al menú de eventos con *CTRL + A* ... ¿no pone las teclas SYM+A en la referencia de teclado?.. Si, en el siguiente bloque explico de que va esto.

## CONTROL y SYM, Emulación y Teclado original.

Por resumirlo de forma introductoria *SYM* significa SYMBOL SHIFT, y es la tecla real del Spectrum, la que tiene físicamente su teclado. *CONTROL* es el equivalente que se usa en los teclados físicos actuales para emular esta tecla (al menos en RVM Mac y Win , así como en Zesarux Mac) que, a día de hoy, ya no existe .

Del mismo modo *CAPS* es la tecla física del Speccy y su equivalente suele ser *SHIFT IZQUIERDO* en los teclados actuales. Cualquier variación debe venir especificada en la documentación del emulador (o en su caso el ZX-UNO por ejemplo), incluso puedes reasignar teclas en algunos o usar las funciones del sistema operativo para cambiar ciertos atajos. Tus necesidades y gustos personales te guiarán en esto, pero te sugiero que al menos una vez lo manejes sin reconfigurar nada.

## Editando Código

En sí, el editor de código de AGD creo que está relativamente bien planteado, sin embargo, la ventaja que supone el que AGD corra en la máquina directamente, se torna en desventaja a la hora de atender a las combinaciones de teclado, y es que los layouts de teclado han cambiado bastante desde los 80 y no siempre es intuitivo manejar un spectrum , por muy bien que esté integrado un emulador.

Para tratar de subsanar esta brecha digital, trataré de darles algunos consejos básicos:

### Escribir y Borrar

En sí escribir es muy similar a un editor actual, con algunas particularidades:

Hay dos modos de borrado, al que estamos habituados, que se realiza mediante la tecla borrar habitual, y otro en que borra \"hacia delante\" desde el carácter seleccionado, que no recomiendo usar.

Intro funciona tal cual, insertando un salto de linea, de ahí que para volver al menu de eventos no se use esta tecla, sin la combinacion SYM+A

Insertar y Sobrescribir es algo que, si no sabemos reaccionar, puede ser fuente de frustración hasta el punto de abandonar el trabajo. Sirva decir que el editor tiene do \"modos\", uno de ellos inserta caracteres en la posición del cursor (a lo que estamos acostumbrados), y otro va sobreescribiendo caracteres ya existentes, esto último puede ser útil en ciertas ocasiones, pero si nos ocurre que estamos \"atrapados\" en él y no sabemos salir, SHIFT IZQUIERDO + 4 es tu billete de vuelta al modo normal.

El modo *E*xtendido del Spectrum es algo que puede dar lugar a confusión también, es algo así como el equivalente a pulsar la tecla AlT en un teclado actual, dándonos acceso a caracteres adicionales, pero en el Speccy es un \"modo permanente\" en el que se entra y se sale. Si te quedas atrapado y no puedes escribir normalmente o insertar saltos de línea, probar con SYM+CAPS (CONTROL + SHIFT IZQUIERDO) puede ser, de nuevo, tu billete a la normalidad.

### Caracteres Especiales

Cosas tan sencillas como escribir un signo igual , si no estamos acostumbrados al teclado de un spectrum pueden ser un gran quebradero de cabeza (el caso del Igual se saca usando *CTRL + L*), personalmente programo con el manual de mi +2A (el físico) en la mesa, esto me permite consultar la referencia de caracteres y pulsaciones de teclas que contiene, cuando la combinaciones que me son naturales, no obtienen el resultado deseado en el editor.

Si no tienes el libro físico, quizá te interese [esta web que contiene dicha información sobre el layout de ZX Spectrum 🌐🟡③](http://slady.net/Sinclair-ZX-Spectrum-keyboard).

### Cortar y Pegar

Desconozco si existe Copiar, pero no he encontrado como hacerlo. Solo podemos cortar y pegar.

Cortar y Pegar si, pero linea a linea, de una en una, por lo que os recomiendo que penseis bien antes de escribir xD.

Las combinaciones son CTRL+Y para cortar y CTRL+U para pegar, nada intuitiva, por lo que, de nuevo, no es lo que mejor hecho está en AGD.

Lo dicho, una vez dominado, es facil, pero hay que trabajarlo un poco para ser eficaz editando código, si tienes alguna duda y no encuentras solución, ¡no dudes en consultarme y trato de daros una mano!

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si no tienes claro porqué querrias editar código, pasa a la página 1]]
* [[Tutorial de AGD 2018 Capítulo 13 - Manual de uso del Editor de Código ⚫①|Si no quieres mas "código" en tu vida, aunque sepas que es necesario lánzate a tirar código en la página 13]]
* [[Tutorial de AGD 2018 Capítulo 14 - Conectando panallas entre si  ⚫①|Si has estado "conectando" con tu niño interior y estás listo para construir jardines, pasa a la página 14]]

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

![[Plantilla - 1MT#One More Thing]]