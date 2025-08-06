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
created: 2025-08-01T03:59:54.205Z
modified: 2025-08-06T22:53:54.057Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 20 - Creando Objetos ⚫①

![Objetos en AGD](PublicBrain/_resources/344ebafb9a7ffc3efe95529b5f686786_MD5.jpg)

* [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 19 - Ciclo de vida ⚫①|<< Anterior]] | [[Tutorial de AGD 2018 Capítulo 21 - Menú de Presentación ⚫①|Siguiente >>]]

En [[MOS Games - The Big Javis Adventure - ZX Spectrum - 2017|The Big Javi´s Adventure]] tenemos por objetivo recolectar 60 objetos repartidos por todo el mapeado. Veamos como se hace esto.

Empezaremos en el capítulo de hoy por el Editor de Objetos, a este editor se accede desde el menú principal, pulsando "O - Objects". Accedemos a una pantalla en la que podremos editar los objetos.

![Editor de objetos de AGD](PublicBrain/_resources/6d0f66d3533b4030991e820d7b8705bd_MD5.jpg)

En esta pantalla básicamente usamos el editor que ya aprendimos a manejar con los sprites, pero en relación con los diferentes objetos que habrá en nuestro juego. Veamos las teclas:

```pre
* X = Insertar nuevo objeto
* D = Borrar objeto actua
* C = Limpiar la imagen del objeto actual
* M = Copiar la imagen del objeto al portapapeles
* K = Pegar la imagen desde el portapapeles
* N = Moverse al siguiente objeto
* L = Moverse al último objeto
* Q = Restar uno al numero de pantalla inicial del objeto
* W = Sumar uno al número de pantalla inicial del objeto.
* P = Establece la posición exacta del objeto dentro de la pantalla indicada.</pre>
```

En esencia usaremos cursores y space para dibujar el objeto, Q y W para establecer el número de pantalla en el que estará inicialmente el objeto.

Una vez hecho esto, mediante P accederemos a un interfaz muy similar al de [[Tutorial de AGD 2018 Capítulo 16 - Nuestro primer enemigo. ⚫①|situar sprites]], pero que nos permitirá situar el objeto actual usando los cursores.

Con intro volveremos al editor del objeto y con una segunda pulsación de Intro al menú principal.

## Recogiendo el Objeto

En el caso de JBA, este proceso se realiza en el código de manejo del personaje en el que se ejecutar una instruccion [[Tutorial de AGD 2018 Capitulo 10 - Referencia del Lenguaje ⚫①|DETECTOBJ]] que nos permite saber si el jugador está sobre algún objeto del escenario y se comprueba OBJ.

Si OBJ contiene un objeto (es decir no vale 255), se toma con GET OBJ y se procesa la acción. La interacción con objetos en JBA es la más simple posible, en algún momento del futuro quiero hacer una videoaventura estilo Dizzy y exploraré más en detalle el sistema de objetos e inventario.

Como suponeis contabilizó el número de objetos obtenidos, y si este llega a los 60 ejecutó ENDGAME para mostrar la secuencia de victoria.

El sistema básico de objeto no tiene más ... la próxima semana trataré el menú de presentación, empezamos a tener casi todas las herramientas en la mano y pronto podre entrar a sonido y música, pero todo a su debido tiempo.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**.  

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si tienes muchos objetos pero poco sujetos, reagrúpate en la página 1]]
* * [[Tutorial de AGD 2018 Capítulo 19 - Ciclo de vida ⚫①|Si ya tienes claro que es un objeto, pero no para que sirven, pasa a la página 19]]
* [[Tutorial de AGD 2018 Capítulo 20 - Creando Objetos ⚫①|Si quieres hacer fortuna en eBay, pasa a la página 20]]
* [[Tutorial de AGD 2018 Capítulo 21 - Menú de Presentación ⚫①|Si tienes curiosidad por ver lo que depare el destino de la humanidad, pasa a la página 21]]

![[Plantilla - 1MT#One More Thing]]