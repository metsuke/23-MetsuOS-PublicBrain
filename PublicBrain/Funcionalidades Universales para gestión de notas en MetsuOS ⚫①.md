---
iaStatus: 8
iaStatus_Model: Raúl Carrillo Garrido aka metsuke
iaStatus_Generado: H
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-07-11T19:55:25.675Z
modified: 2024-09-09T23:42:30.485Z
supervisado: ""
ACCION: S
ver_major: 0
ver_minor: 4
ver_rev: 4
nav_primary: 
nav_secondary: 
tags:
---
# Funcionalidades Universales para gestión de notas en MetsuOS ⚫①

[[Index]] | [[Creando MetsuOS ⚫①]] | [[Funcionalidades Universales para un programa de gestión notas según Emowe  ⚫①]]

Como muchos de vosotros sabéis, la base de mi PublicBrain está disponible online, casi en tiempo real, en este [repositorio de GitHub/Metsuke/PublicBrain](https://github.com/metsuke/23-MetsuOS-PublicBrain)), en forma de Vault de Obsidian (plugins y css incluidos), para que puedas ver los datos en que se basa el despliegue online de MetsuOS (el contenido en sí está registrado en Safe Creative, así que úsalo como ejemplo unicamente)

Una parte importante de MetsuOS se base en la creación y uso de diferentes cerebros digitales, como ejemplo podemos destacar PublicBrain con contenido público que se convierte en web, y PrivateBrain que sirve para uso propio y gestión de libros físicos y su contenido, y, en general elementos no publicables en abierto. 

No obstante no serán esos dos los únicos Cerebros Digitales que contendrá, si bien MetsuOS es una herramienta con funciones específicas, concretas y no genericas, si quisiera mantener una forma de funcionar que aprendí de Emowe cuando empecé con Notion y sobre todo Obsidian, basado en sus principios universales de forma que, cualquier usuario de MetsuOS no esté atado a el de forma obligatoria y sobre todo, que pueda usarlo con parte de su sistema, teniendo la libertad de trabajar sus datos como considere oportuno. 

MetsuOS aporta funcionalidad, pero no se apropia de los datos, de hecho, tiene entre sus objetivos protegerte de la marabunta de datos externos y del bombardeo constante de desinformación, pero de eso, ya hablaremos. 

Paso a comeraros de forma introductoria en que se traduce esto a la hora de construir MetsuOS:

## No dependencia de un proveedor

Puede sonar ilógico siendo que MetsuOS también aspira a ser una linea de productos, pero no quiero acabar haciendo lo que Spotify, o mejor dicho , no hacerlo por exigencias de accionistas. Eso requiere que el centro siempre sea el usuario de forma que, en cuanto el proyecto no vaya en la direccion eticamente correcta, los usuarios puedan abandonarlo.

Además, no viviré para siempre, así que puede que ayude a muchos a avanzar su camino, pero mas gente tendrá que tomar el relevo, y la naturaleza del proyecto implica que no sea software libre en su totalidad, para poder mantener una dirección firme.

Eso no quiere decir que no haya elementos que puedan llegar a ser GNU, pero por ejemplo, la accesibilidad no es opcional y, si ya es problematica en software comercial, en SL entran los egos y comodidad de los componentes y eso lamentablemente acaba siendo mortal para la accesibilidad.

## No dependencia de internet (para acceder a tus datos)

El modelo de MetsuOS tendrá una parte coordinadora en servidor , pero eso no quiere decir que tengas que perder acceso a tus datos desde el servidor, el mejor modo para esto, es hacer que los datos estén bajo el control del usuario, no de la aplicación. 

## Orientación a Notas Atónicas y Conectividad (Zettelcasten)

En tiempos de IA, es VITAL poder gestionar, trazar y controlar no solo tus datos, sino tu conocimiento. Esta metodología es base tanto de mi trabajo personal como de MetsuOS, y esencialmente es la bae de obsidian, aunque no apliquemos la metodologia de forma 100% canónica (Ya vereiis porqué más adelante),

## Contenido en ficheros de texto planos (markdown de preferencia) que podamos trabajar también desde fuera de la aplicacion.

De nuevo, los datos son tuyos y, siempre que respetes lo que requiere MetsuOS para entenderlos, deberías poder modificarlos a tu antojo, así como emplear tu propio código o incluso IAs para modificar y trabajr con - insisto - TUS DATOS.

## Conectoma (enlaces entre notas) limpio y en claro, en las notas, de forma que sean perfectamente trazables y modificables desde fuera de la aplicación.

De nuevo obsidian, que usa el sistema de enlaces internos de Wikipedia y el de enlaces externos de Markdown, me ha desmostrado que es el más eficaz, y, por tanto, MetsuOS es quien interpretará los datos, no tomará control obligatorio sobre ello.
## Metadatos asociados directamente con las notas.

De nuevo, asumo la metodología del propio obsidian, aunque, obviamente MetsuOS lo afina y define sus propios elementos.

## Facilidad de refactorización abriendo varias notas a la vez.

Aunque obsidian es la base sobre la que trabajar con datos, me apunto hacer esto para el editor que probablemente lleve en paralelo MetsuOS.

## Plugins de comunidad que expandan la funcionalidad

Aquí es donde difiero un poco del concepto de SL, la extensión vendrá de la mano de aquello que se cree para trabajar con los datos y que complementen a MetsuOS, pero, al menos en primera fase, no habrá plugins.

Lo que si es posible haya posteriormente es aceso parcial a una parte de la API, mediante un facade que exponga publicamente (para usuarios con cuenta claro), determinadas funciones ya consolidadas, esto es un concepto inicial que ya se desarrollará llegado el momento.

## Conclusion

Esto es un documento vivo, que irá evolucionando iteración tras iteración, pero es la fuente de verdad para MetsuOS o, al menos, la más actualizada posible.

![[Plantilla - 1MT#One More Thing]]