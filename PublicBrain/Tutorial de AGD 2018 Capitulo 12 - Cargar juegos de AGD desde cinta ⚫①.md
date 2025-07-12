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
created: 2025-07-06T19:48:03.398Z
modified: 2025-07-12T20:03:56.934Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 12 - Cargar juegos de AGD desde cinta ⚫①



![Dibujo de una cinta de ZX Spectrum](PublicBrain/_resources/36775e1966ad031619ec351accd6184b_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 11 - Tipos de Tiles ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capítulo 13 - Manual de uso del Editor de Código ⚫①|Siguiente >>]]

 Hace unos dias, me pidieron ayuda para poder cargar [[MOS Games - The Big Javis Adventure - ZX Spectrum - 2017|The Javi's Big Adventure]] en el interfaz de AGD, pues resultaba un poco confuso. Prometí un tutorial al respecto, y aquí va :) 

## La Máquina Virtual

 Lo primero a tener en cuenta es que, en su dia, desarrollé el juego en una máquina virtual de [Retro Virtual Machine 🌐🟡③](https://www.retrovirtualmachine.org/), configurada como un +2 Gris Español, por ello, es la configuracion que uso siempre, a más de ser mi favorita entre las máquinas spectrum de la época, y la que personalmente percibo como "verdadero" Spectrum (es lo que tiene que sea tu primer ordenador...) 

![La maquina virtual sin encender](/PublicBrain/_resources/6f5f3e1c1928a6fc9d7c7568b9652319_MD5.jpeg)

 Claro está, al iniciar el sistema, nos encontramos la máquina apagada (yo uso RVM, pero puedes usar tu emulador favorito), procedemos a encenderla y entraremos en el menú principal. 

  
![Menu principal de nuestro +2 Gris](PublicBrain/_resources/bf51d603e953d35d5e08f630c98261b4_MD5.jpeg)
## Cargando AGD

 Bien, una vez qu hemos accedido al menú, vamos a proceder con la carga de AGD 4.6, ¿porqué esta versión? por ser la que usé para crear el juego, uno de los errores de diseño de AGD es su ausencia de retrocompatibilidad, así pues has de usar exactamente la misma versión con que se creó para cargar el juego. Para ello entramos en el Cargador de cintas... 

![El Cargador de cintas](PublicBrain/_resources/3f80d2fa532e9cf87629cc5ea139e8d6_MD5.jpeg)

 Una vez dentro del cargador de cinta, abrimos el tap de la version de AGD correspondiente, y pulsamos PLAY, AGD cargará (tarda algo menos de 3 minutos, lo he cronometrado). 

![cargando AGD desde la cinta](PublicBrain/_resources/8f2095e0305eab45bea73e61f7c89aaf_MD5.jpeg)
 
 Tras el proceso de carga, aparecerá el menú principal de AGD, aunque claro está, aún sin datos del juego. Obviamente, pararemos la cinta. 

![Menu principal de AGD](PublicBrain/_resources/ac592eef6ef4a24536e5fb83c83977d6_MD5.jpeg)
## Cargar el Juego

 Desde el menú principal pulsamos L para iniciar la carga de datos de juego, AGD carga solo el bloque de datos del juego, por lo que hemos de cargar el .tap del juego y usar forward para pasar tanto el cargador, como la pantalla de carga, a partir de ahí pulsamos Play y dejamos que la cinta haga su magia (tarda otros tres minutos, también lo he cronometrado). 

![Proceso de carga del bloque de juego en AGD](PublicBrain/_resources/709d9eb8a01f864d6e0edf0b382f8e20_MD5.jpeg)

Tras el proceso de carga, aparecerá una pantalla en la que veremos el famosos mensaje "0 OK, 10:5" y en pantalla algunos marcadores sobre fondo azul. <strong>No te asustes es correcto</strong>, ahora te digo que hacer. 

![Tras la carga, parece que todo se ha roto, pero no](PublicBrain/_resources/f27bc634a0aa3b50489a03666a7c6f32_MD5.jpeg)
## Arrancando de nuevo AGD

 Como comentaba, puede parecer que algo ha salido mal, pero no, dado que hemos usado el cargador de cinta, hemos de arrancar de nuevo AGD a mano, para ello lo primero es pulsar escape hasta ver el menú del +2 y entrar en la opción "128 BASIC". 

![128 Basic tras la carga](PublicBrain/_resources/9ccdbae8bcf3662604ca086d93611207_MD5.jpeg)

 Bien, veremos el cargador, que en un modo 48k carga el propio AGD, podemos observar que la ultima instrucción es un RANDOMIZE USR 24000, la escribimos. 

![128 BASIC con el RANDOMIZE USR 24000](PublicBrain/_resources/ce0be62e7c417de48b5ab2d0d569c57b_MD5.jpeg)

 Y pulsamos INTRO para ejecutar (la instrucción básicamente hace que se ejecute el código máquina a partir de la dirección de memoria 24.000 donde está cargado AGD. <strong>De nuevo no os asusteis</strong>. 

![Menu principal de AGD esta vez con fondo amarillo, parece roto, pero esta correcto](PublicBrain/_resources/5286f8ee11578ca7544223ff19b4162d_MD5.jpeg)

 Si, el fondo es amarillo, sospecho que es el funcionamiento definido por e autor para indicar así que la carga se ha completado satisfactoriamente, o al menos es como yo lo interpreto, tampoco tiene mayor relevancia. 
## Comprobando que el juego está ahí

 Llegados a este punto no nos queda más que cheqear que lo que queríamos cargar está ahí , lo que suelo hacer en estos casos, es pulsar X para asegurarme de que el juego está funcionando. 

![Pantalla inicia de JBA, el juego efectivaemnte ha cargado correctamemnte](PublicBrain/_resources/cab004798397924cefce5cd4035a656d_MD5.jpeg)

 Podemos jugar una partida o entrar al juego y pulsar INTRO para volver al menú principal. 

![Volviendo al menú principal tras chequear que el juego esta bien cargado](PublicBrain/_resources/b634da4e9003cc56265047dd2220a6e0_MD5.jpeg)

 Poco más, a partir de aquí podemos bichear (investigar como es) el juego tal cual lo creé, con sus virtudes y sus defectos, incluso jugar con su código o ver como están hechas las distintas pantallas: 

![El Editor de pantalla](PublicBrain/_resources/bba591ebc6f3a3d1f0135e6e67db008e_MD5.jpeg)

 En el próximo capítulo continuaremos con nuestro juego, mi intención es interconectar tres pantallas a lo ancho (una a cada lado de las que habéis creado), pero mientras, podéis ver como he usado los diferentes tipos de bloque en el diseño de los escenarios. 

 Y sobre todo recuerden, esto es para divertirse, si no disfrutan, habrán perdido el tiempo, ya llegamos varias décadas "tarde" así que podemos recrearnos en los detalles :) 

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si te has quedado atascado por intentar cargar demasiado peso, pasa a la página 1]][[Tutorial de AGD 2018 Capitulo 12 - Cargar juegos de AGD desde cinta ⚫①|Si vas a cargar con todo, permanece atento en la página 12]]2]]
* [[Tutorial de AGD 2018 Capítulo 13 - Manual de uso del Editor de Código ⚫①|Si no quieres mas "cargas" en tu vida, lánzate a tirar código en la página 13]]

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

![[Plantilla - 1MT#One More Thing]]