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
created: 2025-06-02T21:45:37.355Z
modified: 2025-06-10T04:49:10.186Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 14
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①

![Menu Principal de AGD](PublicBrain/_resources/d331958696fd5f055f430f879c2d361e_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capitulo 02 - Qué son los tiles ⚫①|Siguiente >>]]

## AGD: Capitulo uno

¡Hola a todos! comenzamos aquí un tutorial.

Me consta deseado desde hace tiempo por una parte de la scene de habla hispana, que no es otra que la versión en español de [los archiconocidos videos de Paul Jenkinson  🌐🟡③](http://randomkak.blogspot.com.es/p/agd-video-tutorials.html) sobre este fantástico maker.

Además de la cuestión relativa al idioma, esta la cuestión de la versión, aquellos tutoriales datan de 2012 y se refieren a AGD 3.0.

En el momento de escribir estas lineas, estoy usando la versión 4.7 he considerado, por tanto, interesante tomar el relevo y comenzar esta actualización - traducción de dichos tutoriales.

Pero no todo va a ser idéntico, voy a seguir el orden sabiamente indicado en los videos originales, pero habrá cambios.

Con la ayuda de Sergio 'thEpOpE' y otros compañeros, tratare de ampliar y complementar este curso con artículos extra y trucos varios.

Pero vayamos por pasos, primero, esta fase :)

## ¿Porqué tutorial de AGD en texto y no en video? (al menos por ahora)

![Simbolo internacional de la sordera](PublicBrain/_resources/271247068c96f3430cde1413b03b2207_MD5.jpeg)

Sin duda alguna el objetivo final es contar con ambas versiones.

No obstante, cualquier video realmente accesible debe contar con transcripción y/o subtítulos para personas con discapacidad auditiva

Dado el objetivo universal de este tutorial, he creído conveniente crearlo primero en texto.

Mas adelante pretendo usar esta como versión transcrita del Video.

Una vez hechas las dos cosas, la obra estará completa. 

(Nota 2025: La generación de la versión en video, podría ser un interesante ejercicio para practicar con IA aplicada al Retro)

Ademas de la cuestión de accesibilidad, esta la cuestión del guión. No quiero improvisar más de lo imprescindible para enseñar como hacerlo por lo que esta primera versión servirá también como guión para los videos.

Dicho lo cual ¡vamos al lío!

## ¿Que es AGD?

![Avatar de Facebook de Jonathan Cauldwell](PublicBrain/_resources/5b26752dfaeefe317c30063efa24f28e_MD5.jpeg)

Si has llegado hasta aquí sabrás qué es, pero aun así lo comentaré: **AGD** (siglas de _Arcade Game Designer_, o "Diseñador de Juegos Arcade") es un software creado por [Jonathan Cauldwell 🌐🟡③](https://www.facebook.com/jonathan.cauldwell) que sirve para crear juegos arcade. Cuenta con diferentes herramientas, corre sobre la máquina para la que vamos a realizar nuestro desarrollo e incluso incluye una suerte de BASIC que nos permite definir y controlar la lógica de nuestra pequeña obra.

Hay diferentes versiones, pero en este tutorial nos centraremos en la **versión 4.7 para ZX Spectrum**, la última disponible en el momento de escribir estas líneas. En el foro de AGD (en inglés) - ttp://arcadegamedesigner.proboards.com/ - puedes _*(Nota 2025 "podías", hoy dia no esta disponible)*_ estar al tanto de todo lo que se cuece en torno a esta herramienta.

## Al lío: ¿Cómo uso AGD?

![Caja del ZX-UNO](PublicBrain/_resources/cd88d7ac98116b1ab537a3e8e411153a_MD5.jpg)

Nada más fácil. Tras [descargar nuestro Kit de Iniciación 🟡③](https://metsuke.com/assets/dnld/AGD_Starter_Kit_0_3.zip) y descomprimirlo, podemos observar que AGD viene en formato `.tap`, por lo que solo has de cargarlo en tu emulador o máquina habitual.

Lo único a tener en cuenta es que originalmente AGD fue diseñado para **ZX Spectrum 128k**, por lo que es recomendable cargarlo en ese modo. A pesar de todo, yo lo suelo usar mediante _Retro Virtual Machine_ con una máquina _+2 Gris_ y no he tenido problemas, salvo algunas corrupciones de memoria al usar el editor de código y de textos. No puedo afirmar que sea a causa del cambio de modelo, pero tampoco cuesta mucho respetar este requisito para quedarse del lado seguro.

Aún así, no se puede afirmar con rotundidad que usar otro modelo cause problemas concretos, por lo que queda en manos de cada cual si sigue o no esta recomendación.

Mientras cargáis de cinta, os quiero comentar un aspecto importante: **AGD no es retrocompatible**. Lo realizado con AGD 4.6 no puede ser modificado con AGD 4.7, por lo que:

1. Guarda versiones de todos los AGD que uses.
2. Elige muy bien qué versión usas para un juego, porque una vez empezado no podrás cambiar a otra sin reescribirlo todo.

### Ok, ¿y ahora? La carga inicial

Tras la carga aparecerá la pantalla del menú principal que hemos podido ver al comienzo de este capítulo. Esta contiene accesos a través de atajos de teclado a todas las opciones que nos ofrece esta herramienta.

Además de la lista de opciones, en la pantalla de menú aparece:

- La versión actual de AGD en la esquina superior izquierda.
- La memoria libre restante en la superior derecha. Es importante revisar esta memoria regularmente para asegurarnos de que el consumo de memoria para los diferentes elementos de nuestro juego es equilibrado. Si no lo vigilamos, podemos encontrarnos con que no nos queda memoria a mitad del desarrollo.

Si bien acabaremos recorriéndolas todas, para hacer lo más sencilla posible la curva de aprendizaje seguiremos el orden "lógico" establecido por el autor de los videos en inglés, que me parece acertadísimo. En primer lugar, prestaremos atención a:

- **A - Character Editor (Editor de Caracteres)**
- **W - Window Area (Zona de juego)**
- **K - Keys (Teclas)**

## A - Editor de Caracteres (Character Editor)

![Tutorial de AGD: Editor de Caracteres](PublicBrain/_resources/a6d36f600620a940d92a720cce91d663_MD5.jpeg)

Aunque no nos vamos a detener mucho en esta característica, puesto que es bastante autoexplicativa, por motivos de completitud de este tutorial de AGD cabe decir que en esta pantalla podremos redefinir la fuente por defecto del Spectrum para crear tanto nuestras propias letras, como números y símbolos.

Para acceder, pulsamos **A** desde el menú principal. Veremos toda la parrilla de caracteres del juego disponibles, así como el área en la que editaremos el carácter seleccionado.

Para avanzar y retroceder usaremos **N** (Next/Siguiente) y **P** (Previous/Anterior). Una vez seleccionado el carácter que deseamos editar, usaremos las teclas del cursor para movernos por el carácter y la tecla **Espacio** para poner o quitar píxeles.

Una vez todo esté a nuestro gusto, con **Intro** volvemos al menú principal, así de simple.

El editor cuenta con opciones para cargar y salvar fuentes de cinta, pero no lo explicaremos aquí por quedar fuera del objetivo de este tutorial introductorio.

## W - Zona de Juego (Window Area)

![Tutorial de AGD: Pantalla de definición del área de juego](PublicBrain/_resources/8c7f55f86445b877886888a838756bc6_MD5.jpeg)

Lo primero que hemos de indicar en nuestro juego realizado con AGD es el área de pantalla. No se debe elegir a la ligera, puesto que una vez definida, si la cambiamos, AGD borrará gran parte del trabajo realizado hasta el momento.

Tomemos nuestro tiempo para decidir si queremos un juego horizontal o, en general, cualquiera de las configuraciones posibles.

Para definirla, AGD nos lo pone muy fácil: tan simple como usar las teclas:

```pre
TECLAS
======= -------------------------------------
- 1/2 para aumentar o disminuir el tamaño horizontal.
- Q/A para variar el tamaño vertical.
- 5/6/7/8 para mover el bloque (formado por los cuadrados rojos y negros) por la pantalla.
```

Es en esta área de cuadros de color donde nuestro juego cobrará vida. Una vez definido, tan simple como pulsar **Intro** y volvemos al menú principal.

**Recordad**: Si lo cambiáis, AGD borrará todas las pantallas creadas y las posiciones de los sprites (gracias, Sergio), así que ¡decidid con cuidado cómo será vuestra área de juego antes de lanzaros a desarrollar el resto!

## K - Teclas (Keys)

![Tutorial de AGD: Pantalla de selección de teclas](PublicBrain/_resources/9a5009f7fac27c93f249c9d87e11ca89_MD5.jpeg)

Para concluir esta primera parte de nuestro tutorial de AGD, vamos a decirle al entorno cuáles serán nuestras teclas de control.

Para ello, pulsamos **K** y el sistema nos pedirá (atención, que aquí pide las teclas en un orden cuando menos fuera de lo común):

- Derecha
- Izquierda
- Abajo
- Arriba
- Disparo
- 2 más asignadas como 6 y 7 que pueden servir a cualquier propósito que deseemos.

Una vez finalizada la selección, el editor nos lleva automáticamente al menú principal.

Tengamos en cuenta que estas serán las teclas que AGD detecte cuando creemos el código que controla a nuestro protagonista. Por ello, tengamos cuidado al definirlas y, sobre todo, **apuntadlas en algún lado** para poder consultarlas, ya que AGD no ofrece modo alguno de "visualizar" cuáles son las teclas definidas actualmente.

Esto será tanto más importante cuando empecemos a usar teclas para acciones que, a priori, no sean las mismas que para las que fueron pensadas.

## Recapitulando

![Pantalla de carga de The Big Javis Adventure](PublicBrain/_resources/944ab7fdce26b6a4483ee2fd581eabd7_MD5.jpeg)

En esta primera aproximación hemos aprendido el manejo básico del editor, así como definido caracteres, área de juego y teclas.

En la segunda parte proseguiremos nuestro camino para lograr crear nuestro primer juego con AGD.

Solo una cosa más: les ruego encarecidamente que no se limiten a seguir los pasos de este tutorial de AGD como autómatas. Experimenten, prueben, pierdan el miedo a romper, pues es la única forma de aprender: perder de vista la costa y, si es necesario, volver a nado.

## ¿Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si lo habitual es que no tiles, quédate en la página 1]]
* [[Tutorial de AGD 2018 Capitulo 02 - Qué son los tiles ⚫①|Si tiles y leones son todos campeones, pasa a la página 2]]
## Referencias Bibliográficas

* [Los videos sobre AGD de Paul Jenkinson  🌐🟡③](http://randomkak.blogspot.com.es/p/agd-video-tutorials.html) 

## Lang
* [[Tutorial d'AGD 2018 Capítol 01 - L'Inici ⚫①|CA]] | [[AGD 2018 Tutorial Chapter 01 - The Beginning ⚫①|EN]] | **[[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|ES]]**

![[Plantilla - 1MT#One More Thing]]