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
created: 2025-11-07T07:21:12.998Z
modified: 2025-11-11T06:59:22.208Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 12
nav_primary: []
nav_secondary: []
tags: []
---
# De Software Libre, Licencias y Filosofías en entornos VUCA 🟡③

[Apps](https://metsuke.com/apps.html)

> **Nota:** Contenido en proceso de refinamiento (WIP).

Esta reflexión nace de una experiencia personal y práctica, tras años desempeñando roles muy diversos en el mundo del software. Aquí expongo la visión que guía mi forma de desarrollar, con la intención de explicarla de manera clara y estructurada, como se hacía antes.

Esta filosofía está profundamente ligada a mi ideología política y técnica: el [[Blog - El Antiintromisionismo, una propuesta filosófica y práctica 🟡③|Antiintrusionismo]] - . Su principio central es sencillo: dar libertad al usuario, pero sin imponerle cómo debe usarla —un error que, en mi opinión, lastra al movimiento GNU—.
## Contexto técnico

El modelo GNU tiene un propósito noble: proteger la libertad del usuario. Sin embargo, cuando se aplica con rigidez ideológica, resulta impracticable para la gran mayoría. Por su parte, el software privativo, condicionado por estructuras empresariales y la presión de accionistas obsesionados con las hojas de cálculo, suele terminar sirviendo más a los intereses financieros que a las necesidades reales de quien lo usa.

No pretendo demonizar ninguna opción —ni el software libre radical ni el propietario—. Discrepo, por ejemplo, con enfoques como el de Richard Stallman, que a mi juicio reflejan un sesgo libertario que ignora la complejidad y diversidad de la naturaleza humana. Todas las posturas son necesarias y, en realidad, se complementan.

En resumen, veo al modelo GNU como el **coche escoba** de la innovación: imprescindible para empujar al pelotón, pero incapaz de liderarlo solo. Sin la presión competitiva del componente privativo, GNU tiende al estancamiento técnico y a la autocomplacencia, desconectándose de las verdaderas demandas de la mayoría. A la inversa, un ecosistema exclusivamente privativo deriva en la **tiranía de las métricas financieras**, fomentando monopolios cómodos y poco innovadores.
## Estructura de licencias propuesta

Para evitar estos extremos, organizo mis desarrollos en **cuatro capas licenciales**:

- **GFan Edition**: Núcleo bajo licencias GNU, formado por primitivas genéricas y unificadas al estilo de las utilidades Unix. Actúa como base interoperable y sólida de modulos básicos (ver consecuencoias del [[Blog - El Antiintromisionismo, una propuesta filosófica y práctica 🟡③|principio de no intromisión]] que exige liberar el código del yugo de GPL siempre que sea posible, si no hay una razón lógica para mantener las restricciones.)
	- Salvo excepciones, la preferencia serán licencias GPLv3, GPLv2, MIT y compatibles, si alguna de las licencias GPL (especialmente la v3 impide alguna cuestion de MetsuOS se reimplementará como GPTv2 con código MIT, atendiendo al principio de no intromisión)
	- Del mismo modo, esta capa quedará con el contenido mínimo imprescindible, cualquier cosa que pueda ser implementado en la Community Edition, por el principio de no intromisión, será implemenmtado en aquella, salvo que la lógica implique la necesidad de usar esta capa para proteger o hacer viable el proyecto MetsuOS.
- **Community Edition**: Capa bajo licencias permisivas (MIT y equivalentes), que extiende GFan con código adicional para ofrecer herramientas y funciones de alto nivel accesibles a toda la comunidad.
- **Pro Edition**: Componente privativo que integra las capas anteriores para proporcionar a profesionales herramientas especializadas, eficientes y optimizadas para entornos exigentes.
- **Enterprise Edition**: Código privativo que aprovecha las tres capas previas para ofrecer soluciones escalables a empresas y equipos de trabajo.

Este enfoque busca fomentar una innovación continua, respetar la diversidad de usuarios y evitar dogmatismos, adaptándose con flexibilidad a entornos VUCA. Se tomarán en cuenta las [[Licencias de Software y compatibilidad entre ellas  🔴②]] a la hora de usar librerias en cada app de cada edición.

## Referencias que apoyan esta visión

1. [Torvalds, L. (2001). Just for Fun: The Story of an Accidental Revolutionary  🟡③🌐](https://www.amazon.com/Just-Fun-Story-Accidental-Revolutionary/dp/0066620732) - HarperBusiness. .- En este libro, Linus Torvalds defiende un pragmatismo en el desarrollo de software abierto (Linux bajo GPL), pero también critica el dogmatismo ideológico del movimiento GNU, priorizando la utilidad práctica sobre la pureza filosófica.
2. [Raymond, E. S. (1999). The Cathedral and the Bazaar 🟡③🌐](http://www.catb.org/~esr/writings/cathedral-bazaar/) - O'Reilly Media .- Eric S. Raymond contrasta el modelo "catedral" (cerrado, planificado) con el "bazar" (abierto, caótico pero eficiente), defendiendo licencias permisivas como las del proyecto BSD frente a las restrictivas de GPL.
3. [Moody, G. (2001). Rebel Code: Linux and the Open Source Revolution 🟡③🌐](https://www.amazon.com/Rebel-Code-Linux-Source-Revolution/dp/0738203335) - Perseus Publishing .-   Analiza cómo la combinación de código abierto y modelos comerciales (Red Hat, IBM) impulsó la adopción masiva del software libre, validando la necesidad de capas privativas para escalar.
4. [Weber, S. (2004). The Success of Open Source  🟡③ 🌐](https://www.hup.harvard.edu/books/9780674018587) - Harvard University Press .-   
   Estudio académico que muestra cómo la diversidad de licencias (permissivas y copyleft) y modelos de negocio híbridos han sido clave para el éxito del software libre.
## Referencias que refutan o matizan esta visión

1. [Stallman, R. M. (2015). Free Software, Free Society: Selected Essays of Richard M. Stallman (3ª ed.)  🟡③🌐](https://www.gnu.org/philosophy/fsfs/rms-essays.pdf) - GNU Press .- Stallman defiende la GPL como herramienta ética indispensable para preservar la libertad del usuario, criticando licencias permisivas por permitir la apropiación privativa.
2. [Free Software Foundation (2020). The GNU Manifesto (versión actualizada) 🟡③🌐](https://www.gnu.org/gnu/manifesto.es.html) .- Documento fundacional que sostiene que cualquier compromiso con software privativo traiciona los principios éticos del software libre.
3. [Coleman, G. (2012). Coding Freedom: The Ethics and Aesthetics of Hacking 🟡③🌐](https://press.princeton.edu/books/paperback/9780691144610/coding-freedom) - Princeton University Press .- E. Gabriella Coleman analiza cómo el idealismo ético del software libre (especialmente en Debian y GNU) choca con enfoques pragmáticos, considerando estos últimos como una forma de cooptación corporativa.  
4. [Kelty, C. M. (2008). Two Bits: The Cultural Significance of Free Software 🟡③🌐](https://twobits.net/) - Duke University Press .- Argumenta que la pureza ideológica del copyleft ha sido esencial para construir comunidades resistentes al control corporativo, y que los modelos híbridos diluyen este poder político.

![[Plantilla - 1MT#One More Thing]]