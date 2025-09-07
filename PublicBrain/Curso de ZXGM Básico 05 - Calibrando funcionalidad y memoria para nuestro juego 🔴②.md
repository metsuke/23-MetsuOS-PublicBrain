---
iaStatus: 8
iaStatus_Model: Grok-3, Veo2, Raúl Carrillo aka Metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-08-23T15:33:03.147Z
modified: 2025-09-07T02:25:56.264Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 7
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursedZapatilla_PoseEsqueletos.mp4
---
# Curso de ZXGM Básico 05 - Calibrando funcionalidad y memoria para nuestro juego 🔴②

![Overbooking en el cementerio](PublicBrain/_resources/e745d2425e42a5571a3f646936010317_MD5.jpg)

* [[Curso de ZX Game Maker ⚫①]]
* [[Curso de ZXGM Básico 04 - Configuración de un nuevo proyecto  🔴②|<< Anterior]] | [[Curso de ZXGM Básico 06 - Pantallas de presentación y transición en el juego 🔴②|Siguiente >>]]

> En la nueva versión, en 128K no me ha dado problemas, si te los da a ti o en 48K te ocurre aquí tienes un método para depurarlo. Los datos de lo que ocupa cada cosa, son de la versión antigua, si obtienes nuevso datos ¡compartelos para mejorar el artículo!.

**Optimizando el uso de memoria en ZXGM**

En este quinto capítulo del curso básico de ZX Game Maker (ZXGM), abordamos el problema de memoria llena identificado en el capítulo anterior. Usando el archivo de mapa de memoria generado por el motor (un archivo map.txt en la carpeta output), analizaremos el uso de recursos y probaremos a desactivar funcionalidades una por una para evaluar el ahorro de memoria. Este enfoque nos permite "cincelar" el proyecto eliminando lo innecesario, liberando espacio para elementos esenciales como sprites personalizados y mecánicas de Cursed Zapatilla: La Excéntrica Cruzada de Sir Patillas.

Continuamos con nuestro ejemplo de juego de plataformas inspirado en Ghosts 'n Goblins, Ghouls 'n Ghosts y Cursed Castilla, ajustando parámetros en Tiled para optimizar bajo las limitaciones del ZX Spectrum (48K/128K). El objetivo es lograr un build funcional sin exceder la memoria disponible, preparando el terreno para capítulos futuros.

Este tutorial asume que has seguido el [[Curso de ZXGM Básico 04 - Configuración de un nuevo proyecto  🔴②|Capítulo Básico 04]] y tienes el proyecto "cursed-zapatilla-zxgm" con el problema de memoria.

## Requisitos previos

Antes de comenzar, verifica lo siguiente (basado en capítulos anteriores):

- Entorno ZXGM configurado con Tiled y el launcher (zxsgm.py).
- Proyecto base de Cursed Zapatilla creado y con build fallido por exceso de memoria.
- Editor de texto para ver el archivo map.txt (e.g., Notepad++ o VS Code).
- Emulador de ZX Spectrum para pruebas post-optimización.
- Acceso a la documentación oficial de ZXGM (enlaces en referencias bibliográficas).

Si no tienes el problema de memoria, simúlalo activando todas las funcionalidades en Tiled para reproducirlo.

## Paso 1: Analizar el mapa de memoria

ZXGM, basado en Boriel Basic, genera un archivo de mapa de memoria (map.txt) en la carpeta output tras cada build. Este archivo detalla las direcciones de memoria Z80 usadas por código, datos y secciones, ayudando a identificar qué consume más espacio.

1. Ejecuta un build fallido: En el launcher, ve a Game/Build. Nota el error de memoria excedida.
2. Abre la carpeta output: Busca el archivo map.txt
3. Interpreta el mapa de memoria:
    - Es un archivo de texto con la direccion de memoria donde comienza algo y su descripcion.
    - La dirección no debe ser superior a (HEX)C000 (dato obtenido de check-memory.py en /bin) 
    - En nuestro caso la direccion de memoria del último bloque es (HEX)C388: .core.__STRLEN, siguiendo el funcionamiento del check-memory.py, si restamos uno de otro nos sale que nos estamos pasando en 904 bytes (<1 KB), parece poco pero teniendo en cuenta que el juego de ejemplo tiene 4 pantallas, me preocupa.
    - Para los calculos voy a usar [Online Hex Calculator  🌐 🟡③](https://www.calculator.net/hex-calculator.html?number1=C388&c2op=-&number2=C000&calctype=op&x=Calculate) que no estoy habituado a restar en Hexadecimal.

## Paso 2: Desactivar funcionalidades y medir ahorro

Probaremos desactivando parámetros en Tiled (Mapa > Propiedades Personalizadas), recompilando y revisando el mapa para cuantificar el ahorro. Me enfocare en funcionalidades de alto consumo identificadas en documentación: música, animaciones, enemigos/tiles max, modos avanzados en primer lugar, pero vamos a hacer un diagnostico completo dirigido al diseño de juegos posteriores.


Registro los ahorros en esta tabla:

> ¡CUIDADO! si relizas tus propias pruebas ten cuidado de guardar el mapa en tiled a disco antes de compilar o parecerá que todo es "gratis" XD
 
| Funcionalidad Desactivada             | Ahorro  (B y KB) | Notas                                                                                                                                                          | Impacto en Juego                                                                              |
| ------------------------------------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| musicEnabled                          | 405B (0.4KB)     | -                                                                                                                                                              | Sin música AY                                                                                 |
| newBeeperPlayer                       | 54B (0.05KB)     | -                                                                                                                                                              | FX básicos                                                                                    |
| maxAnimatedTilesPerScreen (de 10 a 5) | 0B (0KB)         | No tiene impacto en tamaño del juego aunque segurametne lo tenga en el rendimiento.                                                                            | Menos animaciones en los tiles                                                                |
| maxEnemiesPerScreen (de 5 a 3)        | 512B (0.5KB)     | 256B por enemigo extra, algo a tener MUY en cuenta                                                                                                             | Menos enemigos                                                                                |
| goalItems (de 66 a 6)                 | 0B (0KB)         | No tiene impacto                                                                                                                                               | Menos objetos a recoger                                                                       |
| itemsEnabled                          | 39B (0.03KB)     | Evaluamos si visualizar o no cosas en el marcador tiene impacto significativo (asumimos que las funciones equivalentes para otros elementos funcionan igfual). | No se muestra el marcador de Items                                                            |
| hiScore                               | 413B (0.4KB)     | Esta funcionalidad se lleva un buen pellizco de memoria.                                                                                                       | No hay puntuación in-game ni el guardado de la misma para que aparezca en la pantalla de menú |
| messagesEnabled                       | 359B (0.35KB)    | Era previsible que algo llamado "Mensajes" ocupara algo de espacio.                                                                                            | No hay mensajes de ayuda al interactuar con diferentes elementos del juego.                   |

En un proceso normal se Itera hasta que quepa en 48K/128K, pero va ir mas allá, tomaremos la tabla y razonaremos los cambios de configuración que realizaremos.

## Paso 3: Reevaluación de la configuración

Los tres elementos que más han impactado han sido la musioca AY (de la que por razones obvias no queremos prescindir), los dos enemigos extra por pantalla (que de momento quitaremos para dejar un maximo de 4) , la funcionalidad Hi-Score (que deactivaremos por ahora, seria deseable, pero no a ese coste) y Mensajes (que tambien desactivaremos aumentando la carga de información en el manual y/o pantalla de intro).

Lo ganado con Mensajes lo invertimos en un enemigo más por pantalla, que creo dará bastante juego, sabiendo que podemos (aunque no queremos), reducir uno mas si fuese necesario.

En lo personal si me toca reducir más me planteare si reduzco un enemigo o intento optimizar el codigo internamente (de nuevo probablemente esté siendo naif pero debo intentarlo llegado el caso).

Otros elementos que ahora considero irrenunciables como el IDLE, los evaluaremos para su desactivación si y solo si no queda otro remedio, cosa que veremos mas adelante en el desarrollo.

Con esto deberiamos ganar los 900 bytes que nos faltan compilar, y espero no tener que tocar aspectos de memoria durante el proceso de desarrollo (intuyo que estoy siendo naif al desear esto, en 8bits la pelea es contra la memoria xD)

Si todo va bien ahora, en el proximo capítulo empezamos a crear screens (y me da que a llorar por falta de memoria, tambien jajaja).

## Paso 4: Verificación post-optimización

1. Recompila final: Game/Build sin errores.
2. Prueba en emulador: Carga .tap, verifica carga sin crashes.
3. Revisa mapa.txt: Confirma uso < límite (HEX)C000

Parece que, por ahora, prueba superada.

![Parece que esta vez si](PublicBrain/_resources/1150692291c3e6f19c9f686be279a6bd_MD5.jpeg)

## Solución de problemas comunes

- map.txt no generado: Build fallido; revisa logs en terminal.
- Memoria aún excedida: Desactiva más (e.g., keysEnabled, itemsEnabled).
- Emulador crashes: Verifica modo 48K/128K coincide con enabled.

Consulta la documentación y en el grupo Telegram ZXGM cuya direccion podrás encontraren ella.

## Conclusión

Hemos optimizado Cursed Zapatilla liberando memoria al desactivar funcionalidades no esenciales, usando el mapa de memoriap para guiar. Ahora, con espacio, procedemos a agregar pantallas escenarios y sprites en próximos capítulos. ¡El cincel está afilado!
 
## Referencias Bibliográficas

* Mis pruebas de campo ⚫①
* [Documentación oficial del proyecto 🌐🟡③](https://gm.retrojuegos.org/index.html)
* [Repositorio de Github de ZX Game Maker 🌐🟡③](https://github.com/rtorralba/zx-game-maker) .
* [Página de Itch.io del proyecto 🌐🟡③](https://juntelart.itch.io/zx-game-maker)

![[Plantilla - 1MT#One More Thing]]