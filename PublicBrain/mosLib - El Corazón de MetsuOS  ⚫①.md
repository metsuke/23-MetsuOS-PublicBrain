---
iaStatus: 8
iaStatus_Model: Raul Carrillo aka Metsuke
iaStatus_Generado: H
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-11-06T22:37:45.290Z
modified: 2025-11-10T22:28:28.834Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
---
# mosLib - El Corazón de MetsuOS  ⚫①

![mosLib Icon](_resources/4b08d9c1c1d378d5df3ac0dd6de347a0_MD5.jpg)

> OJO WIP 

[Apps](https://metsuke.com/apps.html)

No me ha gustado nada la deriva que las IA querian darle a este proyecto, en eso se nota que siguen la trayectoria mayoritaria, que es justo un camino que no pretendo recorrer con MetsuOS. Es por eso que, aunque me lleve mas tiempo y formalmente sea quizá menos eficiente,  voy a diseñar y construir la estructura a mano. 

En esencia mosLib debe ser la base que unifique las funciones de forma que se ejecuten de forma identica en todos los sistemas operativos, incluido MetsuOS puro, encapsulará las diferencias entre sistemas operativos aportando una coleccion de funciones en modulos (ya veremos que nivel de orientación a objetos) y seran estas las que se emplearán en los modulos y aplicaciones del sistema.

## Estructura y Ediciones

Definiré aqui la estructura general de la libreria y su morfología:

* *GFan Edition* (Licencias GPL y compatibles) .- Esta edicion contiene en forma de modulos con funciones funcionando como appps independientes, las primitivas básicas, modulos con funciones para leer y escribir archivos, leer y escribir el sistema de ficheros, y todo lo que sea necesario, incluyendo accesibilidad.
* *Community Edition* (Licencias MIT y compatibles) .- Esta edición usa las apps indepenmdientes de GFan y construye apps mas complejas o aquellas sencillas que no tienen forma de ser creadas GFan.
* *Pro Edition (Privativo)* .- Crea herencia y polimorfismo sobre los conceptos y apps de las ediciones GFan y Community aportando metodos mejorados de trabao en bloque monousuario.
* *Enterprise Edition* (Privativo) .- Crea herencia y polimorfismo avanzados sobre los concepptos y apps de las ediciones GFan, Community y Pro, orientada a la gestion de tareas y procesos multiusuario distribuido, de forma que equipos puedan trabajar juntos manteniendo cada uno sus instancias de MetsuOS.

## La implementación real

### Generalidades

Toda app de mosLib tiene, de base una pila donde se almacenan las peticiones, gestionada por tres funcionalides, recepcion, ordenación y procesamiento.

La primera funcion toma nota de las acciones solicitadas y las guarda en un formato de pila basado en fichero de texto plano, con campos de datos en forma de tupla específico de la app y sus opciones).

La segunda se encarga de leer esos parametros y trasladar las peticones a tres subpilas: TiempoReal, Fast y Slow, la primera gestiona las peticiones mas urgentes, la segunda las de ejecucion corta (menor de 3 segundos - decidio arbitrariamente), y la tercera para aquellas tareas que tardan más de 3 segundos. Tomará datos de ejecicion de la tercera para evaluar que configuraciones debe mandar a uno u otro. Existirá tambien la posibilidad de asignar RT, F o S a las tareas al solicitarlas para aquellos lugares que requieran configuración específica.

La tercera  se encarga de ejecutar los pendientes, primero todo el RT, segundo todo lo de fast y finalemnte lo de slow. Guardará estadíticas de parametrizacion vs tiempo de ejecucion para indicarle a la parte de ordenación como debe actuar cuando no se especifique el parametro RT, F, o S.


### GFan Apps

### Community Apps

### Pro Apps

### Enterprise Edition Apps




![[Plantilla - 1MT#One More Thing]]