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
created: 2025-09-01T18:06:52.967Z
modified: 2025-12-25T20:46:35.687Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: []
nav_secondary: []
tags: []
---
# Pixel Art Attack - Cursed Zapatilla - ZX Spectrum - Pantalla de Carga ⚫①

![Conversion 1:1 de la imagen origen](PublicBrain/_resources/f0679c5d61a4dde79174bc8fcb57d218_MD5.jpg)

* [[Pixel Art Attack - Cursed Zapatilla - ZX Spectrum ⚫①]]
* [[MOS Games - Cursed Zapatilla - La Excéntrica Cruzada de Sir Patillas (En desarrollo desde 2025 - Release previsto 2026)]]

Iniciamos con esta pantalla que nos introduce en el juego durante la carga desde cinta o disco.

## Iteración 000 : El intento de conversión con ZX-PaintBrush

En esta ocasión tomamos la imagen original y buscamos convertirla a src de tamaño y colores correctos a fin de comenzar con una base sólida. Funcionó, aunque el resultado era pobre.

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```

![Caratula de Cursed Zapatillas](PublicBrain/_resources/33d90a6b2fb87f43d9c3829c4f53814e_MD5.jpg)

### Punto de partida 

La imagen de partida, generada por Grok

 --- column-end ---

![Loading Screen Cursed Zapatilla 0001](PublicBrain/_resources/f5ae0ef26feaa587831f514988771420_MD5.jpeg)
### Resultado de la iteración

Este fué el resultado de ese intento, bien, pero muy discreto.

 --- column-end ---
--- multi-column-end

## Iteración 001 : Una base mucho mejor convirtiendo con Retro-X Painter.

Gracias a [NoEntiendo (@crigonza en twitter/x) 🌐](https://x.com/crigonza)  tuve conocimiento de esta herramienta que podeis usar desde [MetsuOS RetroTools Launcher 🌐](https://github.com/metsuke/mos-retrotools-launcher) (de hecho, la imagen del botón de Retro-X es la que me pasó a mi para mostrarme el resultado, con tramado), y que hace unas conversiones muchisimo mejores, y a varios sistemas y configuraciones aademas.

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```
![Caratula de Cursed Zapatillas](PublicBrain/_resources/33d90a6b2fb87f43d9c3829c4f53814e_MD5.jpg)

### Punto de partida 

Nuevamente, la imagen de partida, generada por Grok, descartando el resultado del intento anterior.

 --- column-end ---

![El punto de partida en resolucion y colores reales de la pantalla de carga](PublicBrain/_resources/b85ed565d16525f912d382f516a9bf47_MD5.jpeg)

### Resultado de la iteración

Este fué el resultado de ese intento, una base mucho mas rico y contundente. 

Elegí colores planos porque los tramados quiero formen partre del acabado final, no del punto de inicio, además de que los tramados que introducia la aplicación, si bien técnicamente correctos, me parecían estéticamente pesados y excesivos. 

Ergo control manual en ese punto.

--- column-end ---

 --- column-end ---
--- multi-column-end
## Iteración 002 : Automatizando la conversion con MetsuOS Game Maker Tools

No me he quedado muy satisfecho con la necesidad de usar herramientas de terceros que no necesariamente son de codigo abierto ni multiplataforma, así que, dentro del marco de [MetsuOS Game Maker 🌐](https://github.com/metsuke/mos-game-maker) he decidido invertir tiempo en crear una pequeña herramienta python que, de forma automatica pero controlada por nosotros como comunidad, nos permita llegar al punto de partida de la edición artística manual.

Ya que me pongo empleare tiempo en mejorar el proceso para las versiones Pro y Enterprise, pero para la Community, minimo quiero poder pasar de la imagen original en png a tamaño original, hasta la scr de 256x192 en un solo comando.

De momento este es el resultado, bastante cercano al anterior, pero con una herramienta bajo nuestro control

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```

![Caratula de Cursed Zapatillas](PublicBrain/_resources/33d90a6b2fb87f43d9c3829c4f53814e_MD5.jpg)

### Punto de partida 

Nuevamente, la imagen de partida, generada por Grok, descartando el resultado del intento anterior.


 --- column-end ---

![El punto al que he llegado con MetsuOS Game Maker Tools](PublicBrain/_resources/f1139e8c8ab76b7f55c6cc2f25dd559e_MD5.jpeg)
 
### Resultado de la iteración

Un punto muy cercano al anterior, personalmente pienso que mejor, pues he logrado respetar las calaveras mucho mejor, pero que trataré de mejorar antes de publicar el script

 --- column-end ---
--- multi-column-end

## Iteración 003 : Evaluando el camino para continuar mejorando el conversor de imagenes a ZX Spectrum

Todo este tiempo he estado haciendo algunas pruebas, la conversion 1-1 parece excelente, sin embargo, al reducir el numero de pixels, la cuestión se complica, siempre tengo la opcion de hacerlo a mano, pero por ahora sigamos explorando la metodología, ya que pretendo convertir todo tipo de elementos y a una escala que dificilmente es soportable mediante colaboraciones de pago, mucho menos abusando de la confianza de nadie.

Como vemos, he aplicado diferentes tipos de tramado, y algunos recortes básicos, los resultados actuales son los siguientes...

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```

![Caratula de Cursed Zapatillas](PublicBrain/_resources/33d90a6b2fb87f43d9c3829c4f53814e_MD5.jpg)

### Punto de partida 

Nuevamente, la imagen de partida, generada por Grok, descartando el resultado del intento anterior.


 --- column-end ---

![Conversion 1:1 de la imagen origen](PublicBrain/_resources/f0679c5d61a4dde79174bc8fcb57d218_MD5.jpg)
## State of the art en conversión 1:1

El resultado me parece mas que satisfactorio, aun tengo que trabajar el control del dither y el suavizado de bordes (me inspiraré en lo que se hace en 3D probablemente) pero por ahora es un resultado que me encanta.

--- column-end ---

![NoDitherVersion](PublicBrain/_resources/6259107da7626ad85cd9a6626a855798_MD5.jpg)
## Reduccion 256x192 Sin Dither

Bien pero parece mas un mapa de atributos que una imagen nitida.

--- column-end ---

![Soft Dither Version](PublicBrain/_resources/49b00172a858aae17f95f5a0ce8ccaeb_MD5.jpg)
## Reduccion 256x192 con Dither "Soft"

Mejora sustancial pero aun carece de la definicion que me gustaria., y que he visto en imagenes convertidas a mano.

--- column-end ---

![Medium Dither Version](PublicBrain/_resources/644676818135af544cb4f5ac1ad1f72e_MD5.jpg)
## Reduccion 256x192 con Dither "Medium"

La resolucion no da de si para tanto detalle y el dither no ayuda


--- column-end ---

 ![Hard Dither Version](PublicBrain/_resources/d352930b7db563e9824b12ffa73e9b22_MD5.jpg)

## Reduccion 256x192 con Dither "Hard"

Por favor que alguien llame al antenista que arregle la trasmision xD

 --- column-end ---
--- multi-column-end
### Resultado de la iteración

Esta claro que debo trabajar en dos asppectos, el primero en torno a la versión 1:1 el control del dither y el suavizado de bordes, por otro, una estrategia (probablemente a base de cropping en este primer intento) para quedarme con la parte relevante de la imagen y que la reducción sea mas adecuada a la resolucion objetivo y cuanto puede mostrar. ¡Seguiremos informando!


![[Plantilla - 1MT#One More Thing]]