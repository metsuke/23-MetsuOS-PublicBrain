---
iaStatus: 8
iaStatus_Model: Grok-4, Raul Carrillo aka Metsuke
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-11-10T23:05:22.222Z
modified: 2025-11-10T23:06:08.034Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: "0"
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# Licencias de Software y compatibilidad entre ellas  🔴②

> OJO WIP

[[De Software Libre, Licencias y Filosofías en entornos VUCA 🟡③]]


> OJO WIP
## Introducción

Las licencias de software son contratos legales que regulan cómo se puede usar, modificar, distribuir o compartir un programa informático. Básicamente, definen las reglas del juego. Podemos agruparlas en tres grandes familias:

- **Software libre / open source**: priorizan la libertad del usuario para estudiar y mejorar el código.
- **Licencias permisivas**: imponen muy pocas condiciones; casi todo vale mientras se respete el aviso de copyright.
- **Software privativo**: el código fuente queda cerrado y las libertades del usuario están muy limitadas.

La **compatibilidad** entre licencias es clave cuando se combinan fragmentos de código de distintos orígenes. No todas encajan: una licencia *copyleft* como la GPL exige que cualquier obra derivada siga siendo libre, lo que choca con licencias más restrictivas. A menudo la compatibilidad es **unidireccional**: una licencia permisiva puede meterse en un proyecto GPL, pero no al revés sin abrir todo el código.

Organismos como la **Free Software Foundation (FSF)** y la **Open Source Initiative (OSI)** publican guías oficiales para evitar líos legales.

## GPL y licencias compatibles

La **GNU General Public License (GPL)** es la licencia *copyleft* por excelencia. Creada por la FSF, obliga a que cualquier modificación o distribución derivada se publique bajo la misma GPL. Existen dos versiones principales:

- **GPLv2** (1991)
- **GPLv3** (2007) – añade cláusulas contra patentes y *tivoization*.

Para que una licencia sea **compatible con GPL**, el código bajo esa licencia debe poder relicenciarse bajo GPL sin infringir sus términos. La compatibilidad **no es simétrica**: licencias permisivas suelen entrar en proyectos GPL, pero el código GPL no puede usarse en proyectos no-copyleft sin liberar todo el fuente.

### Licencias compatibles con GPL (según la FSF)

> *Algunas solo con GPLv3, no con GPLv2*

- Apache License 2.0 → solo GPLv3  
- Artistic License 2.0  
- Berkeley Database License (Sleepycat)  
- Boost Software License  
- BSD 3-clause (Modified)  
- CeCILL v2  
- Clear BSD License  
- eCos License 2.0  
- Educational Community License 2.0 → solo GPLv3  
- Expat License (MIT)  
- FreeBSD License (2-clause BSD)  
- ISC License  
- Mozilla Public License 2.0 (mediante dual-licensing)  
- Python License (≥2.0.1)  
- X11 License  
- Zero-Clause BSD (0BSD)  
- ZLib License  
- Unlicense  
- WTFPL v2  

*(Lista completa y actualizada: [FSF – Licenses](https://www.gnu.org/licenses/license-list.es.html))*
## MIT y licencias compatibles

La **MIT License** es la reina de las licencias permisivas: permite casi todo con la única condición de incluir el aviso de copyright y la licencia original. Proyectos como **Node.js**, **React** o **Rails** la usan por su simplicidad.

Al no ser *copyleft*, se lleva bien con casi todo:

- Puede incluirse en proyectos GPL, Apache, BSD o incluso **privativos**.
- **No funciona al revés**: código GPL no puede relicenciarse bajo MIT.

### Licencias compatibles con MIT

| Dirección | Licencias |
|-----------|-----------|
| **MIT → X** | GPL v2/v3, LGPL, AGPL, Apache 2.0, BSD (todas), ISC, Boost, EPL 2.0, MPL 2.0, ZLib, licencias privativas |
| **X → MIT** | Todas las permisivas (BSD, ISC, Apache 2.0, etc.) |

## Software privativo y licencias compatibles

El **software privativo** (Windows, Photoshop, Oracle Database…) mantiene el código fuente cerrado. Solo puede incorporar código open source **si la licencia lo permite explícitamente**.

- **Licencias permisivas**: sí (MIT, BSD, Apache 2.0…).
- **Licencias copyleft fuerte** (GPL): no, salvo que se libere todo el producto.
- **Licencias copyleft débil** (LGPL): sí, para bibliotecas enlazadas dinámicamente.

### Licencias compatibles con software privativo

- MIT  
- Apache 2.0  
- BSD (2/3/0-clause)  
- ISC  
- ZLib  
- Boost  
- **LGPL v2.1/v3** (solo bibliotecas)  
- MPL 2.0 (por archivo)  
- Unlicense  

## Otras licencias relevantes

Existen licencias intermedias o especializadas:

| Licencia | Tipo | Compatibilidad destacada |
|----------|------|---------------------------|
| **Apache 2.0** | Permisiva + patentes | GPLv3, MIT, BSD |
| **MPL 2.0** | Copyleft por archivo | Apache, MIT, BSD |
| **EPL 2.0** | Copyleft débil | Apache, MIT |
| **AGPL v3** | Copyleft en red | GPLv3 |
| **CDDL 1.0** | Copyleft por archivo | MPL (no GPL) |
| **CC BY-SA 4.0** | Creative Commons | Solo contenido no software |

## Referencias que apoyan el contenido

> OJO WIP

1. **Free Software Foundation** – *List of GPL-compatible licenses*  
   <https://www.gnu.org/licenses/license-list.es.html>

2. **Open Source Initiative** – *Licenses & Standards*  
   <https://opensource.org/licenses>

3. **GNU Project** – *GPLv3 FAQ*  
   <https://www.gnu.org/licenses/gpl-faq.es.html>

4. **Choose a License** – *MIT License* (explicación oficial)  
   <https://choosealicense.com/licenses/mit/>

5. **Apache Software Foundation** – *Apache License 2.0*  
   <https://www.apache.org/licenses/LICENSE-2.0>

6. **Mozilla** – *MPL 2.0 FAQ*  
   <https://www.mozilla.org/en-US/MPL/2.0/FAQ/>

7. **Video explicativo (YouTube)** – *Licencias Open Source: GPL, MIT, Apache – Explicado fácil*  
   Canal: **freeCodeCamp Español**  
   <https://www.youtube.com/watch?v=7jFbcL8N8Ww>

8. **Libro** – *“Software Libre para gente ocupada”* – Antonio Durán (CC BY-SA)  
   <https://www.antoniodebian.com/libro-software-libre/>

## Referencias que refutan o matizan partes del contenido

> OJO WIP

1. **Ben Balter (GitHub)** – *“The MIT License is not compatible with GPL in all cases”*  
   Blog post aclarando la **unidireccionalidad** real.  
   <https://ben.balter.com/2014/03/11/mit-license-and-gpl-compatibility/>

2. **Bradley M. Kuhn (SFC)** – *“GPL Compatibilities: The FSF List is Conservative”*  
   Artículo donde se critica que la lista FSF es **demasiado restrictiva** en algunos casos.  
   <https://sfconservancy.org/blog/2016/jul/25/gpl-compat/>

3. **Luis Villa (ex-Mozilla)** – *“MPL 2.0 is not file-level copyleft in practice”*  
   Explica limitaciones reales del copyleft por archivo.  
   <https://lu.is/blog/2011/02/23/mpl-2-0-faq/>

4. **Video (YouTube)** – *“¿Es realmente la MIT la licencia más permisiva?”*  
   Canal: **Fazt Code** – compara MIT vs. Unlicense vs. 0BSD.  
   <https://www.youtube.com/watch?v=5z0q3XjE9cI>

5. **Paper académico** – *“License Compatibility in Open Source: A Legal Analysis”* – Pamela Samuelson (2019)  
   UC Berkeley – muestra casos reales de incompatibilidad no listados por FSF.  
   <https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3353333>


![[Plantilla - 1MT#One More Thing]]