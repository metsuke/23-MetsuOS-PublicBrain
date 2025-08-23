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
modified: 2025-08-23T19:37:17.122Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursedZapatilla_PoseEsqueletos.mp4
---
# Curso de ZXGM Básico 05 - Calibrando funcionalidad y memoria para nuestro juego 🔴②

![Overbooking en el cementerio](PublicBrain/_resources/e745d2425e42a5571a3f646936010317_MD5.jpg)

* [[Curso de ZX Game Maker ⚫①]]
* [[Curso de ZXGM Básico 04 - Configuración de un nuevo proyecto  🔴②|<< Anterior]] | Siguiente >>

> OJO WIP

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
| hiScore                               |                  | -                                                                                                                                                              | No hay puntuación in-game ni el guardado de la misma para que aparezca en la pantalla de menú |
| messagesEnabled                       |                  | -                                                                                                                                                              | No hay mensajes de ayuda al interactuar con diferentes elementos del juego.                   |

En un proceso normal se Itera hasta que quepa en 48K/128K, pero va ir mas allá, ordenemos esta tabla por ahorro de mayor a menor y evaluémoslo respecto del diseño deseado del juego.

XXX

## Paso 3: Reevaluación de la configuración

## Paso 4: Verificación post-optimización

1. Recompila final: Game/Build sin errores.
2. Prueba en emulador: Carga .tap, verifica carga sin crashes.
3. Revisa .map: Confirma uso < límite (e.g., <40KB para 48K).

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