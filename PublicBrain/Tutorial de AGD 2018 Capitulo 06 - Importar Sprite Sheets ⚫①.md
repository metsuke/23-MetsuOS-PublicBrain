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
created: 2025-06-17T10:25:14.495Z
modified: 2025-06-17T14:27:49.220Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 06 - Importar Sprite Sheets ⚫①

![La secuencia de salto del sprite del prota](PublicBrain/_resources/817694b86c4ed96db1dbf6c390bab679_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 05 - Animando sprites ⚫①|<< Anterior]]  | Siguiente >>

Aunque el interfaz de AgD pone fácil generar animaciones, puede que en determinadas ocasiones nos interese trabajar con un grafista y en este caso sea más cómodo que el cree las animaciones directamente sobre un Screen con algun programa de dibujo y que nos lo pase despues para que los importemos, mientras nosotros trabajamos en el resto.

Antes de nada unas pocas teclas que usaremos en el proceso:

```pre
TECLAS
------ ================================
- L = carga una pantalla al editor para copiar trozos
- G = vuelve a la pantalla cargada para copiar otro trozo
- Space en la pantalla cargada = Copia el trozo activo
- Cursores en la pantalla cargada = Mover Cursor de Copia.
- K = Pega lo copiado al frame del sprite en pantalla.
```
## Paso 1: Cargar la Screen en AGD

Lo primero - obviamente una vez disponemos de la pantalla hecha por nuestro colaborador o por nosotros mismos con el spritesheet correspondiente, es cargarla en AGD para trabajar con ella.

![pantalla para Scratchpad cargando](PublicBrain/_resources/966a13018aaf5483c9c1e6c156550c68_MD5.jpeg)

Para lograrlo, lo primero es, si no estamos ya en ella, entrar a la pantalla de edicion de sprites (Letra S desde el menú principal), y una vez dentro, pulsar L. AGD nos preguntará si queremos cargar el "scratchpad" (que es como se llama en el sistema AGD).

Introducimos la cinta que contiene el screen (recordemos la advertencia del propio manual sobre cargas automáticas por parte de los emuladores, página 24), respondemos que si (Y y Enter), la pantalla cambiará a modo carga, momento en que pulsamos play, la pantalla se cargará y queda visible en dos colores, pues estos no se utilizan en esta funcion.

![na vez cargada, aparece un cursor que permite seleccionar un bloque de 16x16](PublicBrain/_resources/0781af4d74e164ca6aa31213a35a1435_MD5.jpeg)

## Paso 2: Seleccionar un bloque, copiarlo y pegarlo

Una vez cargada, el proceso es sencillo, tan solo hemos de movernos con los cursores y pulsa la tecla space, AGD copiara el trozo "iluminado" al portapapeles y volverá a la pantalla de edición de Sprites.

![El cursor de seleccion en un scratchpad situado para copiar un bloque](PublicBrain/_resources/d40aa57113f091d232d7f58f968ec224_MD5.jpeg)

El bloque que hemos copiado funciona a partir desde este momento de forma similar al copiar y pegar habituales, nos situamos en el sprite y frame que corresponda y pulsamos la letra K para pegar.

En el ejemplo estoy copiando un bloque con forma de ojo de una loading screen, en el caso de un spritesheet repetiremos este proceso para cada frame del sprite, en ese caso, una vez pegado el bloque, pulsaremos G para volver a la pantalla desde la que copiamos, seleccionaremos el siguiente bloque a copiar, y vuelta a empezar hasta haber importado todos los necesarios en su lugar.

![bloque recién copiado ya en su lugar de destino, un frame de uno de nuestros sprites](PublicBrain/_resources/7b6eb5c066c4d77da179d45d5b421c30_MD5.jpeg)

## Conclusiones

No es un proceso obligatorio, pero quizá en un flujo de trabajo con más de una persona sea más util que trabajar directamente cada frame en el editor. No es obligatorio elegir un metodo para todo, por lo que depende de cada uno decidir que usa en cada caso.

Un detale que me ha dejado un poco confundido es el uso de "ScratchPad" para nombrar la pantalla del "Spritesheet", mi intuición me dice que el significado oculto proviene de algo similar a "hoja en sucio" o "notas en sucio", pero desconozco si ese es su origen y relación con un videojuego. Si estás leyendo esto y sabes de su origen ¿podrías contárnoslo y mencionarme en twitter/x? ¡gracias!.

En el próximo capítulo quiero empezar a jugar con sprites en nuestra pantalla, empezaré por el protagonista y de ahí iremos viendo diferentes elementos, como los tipos de bloque, enemigos y su lógica, o pasar de una pantalla a otra, pero esas son ¡cuestiones para futuros capítulos! :)

## ¿Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si crees que Scratchpad en este contexto tiene que ver con encuadernar manualidades, pasa a la página 1]]
* [[Tutorial de AGD 2018 Capitulo 05 - Animando sprites ⚫①|Si crees que los sprites son aburridos, pasa a la página 5]]
* [[Tutorial de AGD 2018 Capitulo 06 - Importar Sprite Sheets ⚫①|Si no localizas al instructor de clase, pregunta a un guardia y pasa a la página 6]]
* Si quieres volver a Ventormenta a por la siguiente misión de la cadena, espera que vaya primero y te abro portal desde allí.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

![[Plantilla - 1MT#One More Thing]]