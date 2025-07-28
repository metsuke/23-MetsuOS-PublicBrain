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
created: 2025-07-27T16:57:50.370Z
modified: 2025-07-28T06:28:38.601Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial de AGD 2018 Capítulo 18 - Optimiza tu código ⚫①

![Optimizacion de codigo](PublicBrain/_resources/87bb53230dbe4f7418528d90468c385d_MD5.jpg)

 * [[Tutorial de AGD 2018 Edition ⚫①]]
* [[Tutorial de AGD 2018 Capítulo 17 - Puntuación y Vidas ⚫①|<< Anterio]] | Siguiente >>

Hemos empezado a escribir código en el editor de AGD, y 0quisiera [[Tutorial de AGD 2018 Capítulo 13 - Manual de uso del Editor de Código ⚫①|amploar las instrucciones que comentamos en un capítulo anterior]]

Me gustaría en esta ocasión compartir unas claves básicas antes de continuar con el juego en sí, sobre todo - pero no sólo - de optimización.

## Orden, orden, orden

No hagas como yo, que escribí JBA al completo y no apunté para que usé cada variable, ahora me encuentro optimizando tanto para contarlo como para hacer alguna prueba de código y no se para que sirven todas las variables.

Me va a tocar tomar notas poco a poco para optimizarlo, pero tened por seguro que no me vuelve a pasar, lo mismo para los tipos de sprite, no apunte a que correspondía cada número y he de deducirlo caa vez mirando código.

## Graba antes de tocar (y después)

En estos días tenemos una enorme ventaja, y es que podemos grabar snapshots continuamente desde nuestros emuladores.

Es fácil de hacer y además ocupa poco espacio, hazlo al menos:

* Antes de tocar
* Despues de consolidar una modificación
* Antes de empezar tu sesión
* Antes de parar y concluir tu sesión

Ojala hubiera seguido antes mi propio consejo, me hubiera evitao tener que [[Tutorial de AGD 2018 Capítulo 14 - Conectando panallas entre si  ⚫①|repetir un juego casi al completo]]

## Piensa antes de hacer

Puede parecer de perogrullo, pero no pocos lios han sido resueltos pensando antes de tocar nada en el código, o al menos guadando antes de tocar para poder restaurar tras liarla parda.

Para aprender es bueno tocar y romper cosas, pero cuanto más complejo sea tu proyecto, tanto más importante es que lo hagas con cabeza, sabiendo donde vas y consolidando cada paso. Te evitarás muchos sustos.

## Evita comprobar dos veces lo mismo

Estamos trabajando con un ordenador limitado en cuanto a velocidad y recursos, si en una máquina actual es importante (y profesional) evitar consumir recursos de más, en una de estas máquinas puede ser la diferencia entre un juego fluido y otro injugable.

Como ejemplo, os pongo el código del tipo de sprite 7 de JBA, la gota, básicamente la implementé creando un enemigo que rebota arriba y abajo, solo que cuando sube es invisible, y además no mata cuando no se ve.

Bien, fui torpe y comprobé PARAMA para ver si subimos o bajamos, y tras el movimento volvía a comprobar PARAMA para controlar si debe matar al jugador ... absurdo consumo de ciclos de procesador y de valiosa memoria que se torna más necesaria cuanto más ambicioso es nuestro proyecto.

## Cada cosa a su tiempo

Otra de esas \"cuestiones imprescindibles\" dentro el desarrollo retro, aquí no hay concurrencia, no hay objetos que se ejecutan siguiendo una planificación cuidadosa del sistema operativo, eres tú contra el procesador, no hay más.

Por ello es vital que coloques cada función en el punto que le corresponda, y que esta funcionalidad no impida la fluidez del juego.

## Evita dejar código inútil

Sobre todo cuando hacemos pruebas, es habitual que nos puedan quedar flecos en forma de código que bien no se ejecuta o que aún ejecutándose no tiene funcion real. 

Hemos de revisar regularmente el código para limpiar estas líneas residuales, por una parte para ahorrar memoria y ciclos de ejecución , por otro lado, la limpieza del código es clave para la mantenibilidad del mismo.

## Truco: Eliminar el signo igual para ahorrar memoria

Puedes ganar bastantes bytes eliminando el signo igual en todas las instrucciones LET, en lugar de LET G = 1, usa LET G 1, funcionará igual y ahorrarás memoria. 

### Advertencia: Cuidado con los IF

Asegúrate de que compruebas cada IF y cada ELSE que escribas, sobre todo si contienen condicionales, a veces no fallan al compilar, pero tampoco funcionan como se espera, la regla general es: no escatimes bytes escribiendo esas condiciones y chequea con cuidado.

### Sobre comparaciones en los IF

El IF en AGD no tiene todos los operadores de comparación. Es algo que no está documentado, y que el analizador de sintaxis no comprueba para indicarlo al usuario, pero lo compila mal, porque no existen como tal.

AGD solo entiende los siguientes operadores de comparación:

* =
* <>
* <=
* >

Por lo tanto cuidado, porque < y >= no existen para AGD y si los usas el >= causara que AGD dibuje como dos elementos independientes, y entenderá que son > e = por separado, con lo que dará como resultado una compilación ilógica. 

En el caso de < directamente no lo acepta, y da error como tal

```pre
Un truco para verificar si el código pasa por determinados lugares es usar BORDER n. Si el borde cambia, es que esa parte se ha ejecutado.
```
> Gracias a thE pOpE por la información detallada!

### Precauciones al quitar el signo igual en funciones que se usan dentro de IF

Hay una excepción a la regla de no quitar los signos igual en los IF, pero que debe ser tratada con cuidado, como he dicho en general se debe poner el igual en todas las comprobaciones de variable por ejemplo IF A = 5, pero se puee obviar en caso de funciones, como por ejemplo IF KEY 2 o IF COLLISSION 0, chequea en cada caso por si no funcionara algún escenario que desconozca, pero puedes ahorrar algo más en esos escenarios.

> * KEY y COLLISION no son variables, son funciones que devuelven un valor booleano y llevan un argumento, por eso no llevan = en un IF (IF KEY 2 , realmente sería como poner IF KEY(2) en otros lenguaje de más alto nivel), mi experiencia con eliminar el = en los IF es que parece fallar cuando se usa ELSE **thE pOpE**

## Concluyendo

Una vez que se domina, resulta relativamente sencillo escribir código con soltura, pero a veces el compilaor es algo caprichoso, póngase, por tanto, especial cuiado en estas cuestiones que he indicao.

Un pequeño IF que no se ejecuta tal cual aparenta hacerlo a primera vista, puede tenernos horas - incluso días - buscando un bug en apariencia irresoluble, no des nunca ningun IF por sentado en AGD.

## Referencias Bibliográficas

- **Ninguna fuente verificable disponible**. 

## Y ahora que?

* [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|Si tienes muchos optis pero pocos mizas, presentate en enfermería en la página 1]]
* [[Tutorial de AGD 2018 Capítulo 18 - Optimiza tu código ⚫①|Si crees que puedes mejorar aún más tu código, pasa a la página 18]]
* Si ya has ahorrado hasta el ultimo superbyte 'yo no puedo estar sin el', pasa a la página 19

![[Plantilla - 1MT#One More Thing]]