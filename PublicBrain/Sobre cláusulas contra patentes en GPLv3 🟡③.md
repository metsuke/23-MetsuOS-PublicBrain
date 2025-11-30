---
iaStatus: 8
iaStatus_Model: Grok-4, Raul Carrillo aka Metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-11-16T06:24:54.964Z
modified: 2025-11-18T15:22:11.696Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 8
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: SoftwarePatents.mp4
---
# Sobre cláusulas contra patentes en GPLv3 🟡③

![Softrware Patents](PublicBrain/_resources/5a7834dedd1d62060fa63bc554922154_MD5.jpg)

* [[Licencias de Software y compatibilidad entre ellas 🟡③]]
* [[De Software Libre, Licencias y Filosofías en entornos VUCA 🟡③]]

> OJO WIP
## Introducción

La GNU General Public License versión 3 (GPLv3), lanzada por la Free Software Foundation (FSF) en junio de 2007, supuso un avance importante respecto a su predecesora, la GPLv2 de 1991. Mientras que la GPLv2 se centraba en las "cuatro libertades" del software libre —usar, estudiar, modificar y distribuir el software—, la GPLv3 incorpora protecciones más sólidas contra amenazas modernas, como las patentes de software, la "[[Sobre Tivolización en el software - Significado e implicaciones 🟡③|tivoización]]" (restricciones técnicas que impiden cambios) y acuerdos comerciales que podrían minar la libertad del software.

Las cláusulas contra patentes en la GPLv3 son uno de sus elementos clave. Su meta principal es evitar que las patentes se usen para limitar las libertades que ofrece la licencia, garantizando que el software bajo GPLv3 siga siendo realmente libre y accesible para todos. Estas medidas responden a un contexto histórico en el que las patentes de software se han visto como una amenaza grave para el movimiento del software libre. Por ejemplo, en los años 2000, compañías como Microsoft acumularon patentes relacionadas con tecnologías abiertas, como Linux, y las emplearon para intimidar a usuarios o rivales. Un caso destacado fue el acuerdo de 2006 entre Microsoft y Novell, en el que Microsoft se comprometió a no demandar por infracción de patentes a clientes de Novell que usaban SUSE Linux, pero esto creaba un trato discriminatorio que podría perjudicar a otros usuarios de GPL. La FSF interpretó esto como un intento de dividir la comunidad y respondió añadiendo cláusulas anti-discriminación en la GPLv3.

Básicamente, estas cláusulas contra patentes pretenden:
- Conceder licencias de patentes automáticas y no exclusivas a todos los usuarios y distribuidores.
- Disuadir demandas por patentes mediante mecanismos de respuesta.
- Impedir acuerdos que utilicen patentes para restringir las libertades de la GPL.

A continuación, exploraremos en detalle estas cláusulas, basándonos en el texto oficial de la licencia y en análisis de expertos.

## Antecedentes Históricos y Motivaciones

El proceso de creación de la GPLv3 fue abierto y colaborativo, durando más de un año e involucrando a la comunidad, empresas y juristas. Según Richard Fontana, quien participó en la redacción como asesor de la Software Freedom Law Center (SFLC), el panorama estaba marcado por la hostilidad de Microsoft hacia Linux, litigios como el de SCO contra IBM (que alegaba violaciones de propiedad intelectual en Linux) y un boom en modelos de negocio de código abierto. Las patentes se convirtieron en un foco principal porque representaban una "amenaza existencial": en lugares como Estados Unidos, donde las patentes de software son válidas, un titular podría demandar a usuarios de software libre por infracción, aunque el código sea público.

La FSF, guiada por Richard Stallman, buscaba neutralizar las patentes contra el software GPL. El primer borrador de la GPLv3 (enero de 2006) ya incluía disposiciones contra patentes, pero se pulieron gracias a las opiniones recibidas. Por instancia, el acuerdo Microsoft-Novell impulsó la adición de condiciones permanentes en la sección de patentes para contrarrestar la agresión por patentes. Estas cláusulas no solo protegen a los usuarios, sino que también promueven la colaboración al obligar a los contribuyentes con patentes a compartirlas de forma justa.

Algunos críticos, especialmente en el sector empresarial, argumentaban que complicaban la adopción para compañías con carteras de patentes, limitando su capacidad para monetizar o defenderse. Sin embargo, sus defensores destacan que refuerzan el copyleft (el sistema que obliga a que las derivadas sean libres) al integrar las patentes en el ecosistema libre.

## Análisis Detallado de las Cláusulas Relevantes

Las disposiciones contra patentes se concentran sobre todo en las **secciones 10 y 11** de la GPLv3. Vamos a citar el texto oficial (en inglés, con traducción aproximada al español para mayor claridad) y explicar su significado.

### Sección 10: Licencias Automáticas a Receptores Downstream

Esta sección garantiza que todo receptor de una obra bajo GPLv3 obtenga automáticamente una licencia para ejecutar, modificar y propagar el software, sin restricciones extras. Incluye una prohibición clara contra litigios por patentes:

**Texto clave (traducción aproximada):**
> Cada vez que transmitas una obra cubierta, el receptor recibe automáticamente una licencia del licenciante original para ejecutar, modificar y propagar esa obra, sujeta a esta Licencia. No estás autorizado a imponer restricciones adicionales a los derechos otorgados por esta Licencia. No eres responsable de hacer cumplir el cumplimiento de esta Licencia por terceros.
>
> No puedes imponer ninguna restricción adicional a los derechos otorgados por esta Licencia. Por ejemplo, no puedes imponer una tarifa de licencia, regalía o cargo por el ejercicio de los derechos otorgados bajo esta Licencia, y no puedes iniciar litigios (incluyendo contrademandas o reconvenciones en un juicio) alegando que cualquier patente es infringida por hacer, usar, vender, ofrecer para la venta, o importar el Programa o cualquier porción del mismo.
 
- **Protección contra litigios**: Si un distribuidor inicia una demanda por infracción de patente relacionada con el software GPL, pierde sus derechos bajo la licencia. Esto funciona como una "cláusula de retaliación" (patent retaliation clause), que desalienta a las empresas a usar patentes de forma ofensiva. En el borrador inicial de la GPLv3, esta cláusula no era tan robusta, pero se reforzó para abarcar no solo la distribución, sino también el uso y la modificación.
- **Ventajas**: Protege a la comunidad al convertir las patentes en herramientas defensivas, no agresivas. Empresas como IBM o Red Hat, que contribuyen a proyectos GPL, lo ven como un beneficio porque fomenta la innovación conjunta sin temor a demandas.
- **Riesgos**: Para productores con patentes, reduce su capacidad para demandar por infracciones no relacionadas, lo que podría afectar su posición competitiva. No obstante, análisis como los de LWN.net (2006) indican que la cláusula no es "absoluta": no revoca derechos de mero uso sin copia, y permite términos adicionales opcionales para respuestas limitadas.

### Sección 11: Patentes

Esta es la sección principal contra patentes. Define términos clave y establece la concesión obligatoria de licencias de patentes.

**Texto completo (traducción aproximada, manteniendo la estructura):**
> Un "contribuyente" es un titular de derechos de autor que autoriza el uso bajo esta Licencia del Programa o una obra en la que se basa el Programa. La obra así licenciada se llama la "versión del contribuyente".
>
> Las "reclamaciones de patente esenciales" de un contribuyente son todas las reclamaciones de patente poseídas o controladas por el contribuyente, ya adquiridas o por adquirir, que serían infringidas por algún modo, permitido por esta Licencia, de hacer, usar o vender su versión del contribuyente, pero no incluyen reclamaciones que serían infringidas solo como consecuencia de modificaciones adicionales a la versión del contribuyente. Para propósitos de esta definición, "control" incluye el derecho a otorgar sublicencias de patente de manera consistente con los requisitos de esta Licencia.
>
> Cada contribuyente te otorga una licencia de patente no exclusiva, mundial, libre de regalías bajo las reclamaciones de patente esenciales del contribuyente, para hacer, usar, vender, ofrecer para la venta, importar y de otra manera ejecutar, modificar y propagar el contenido de su versión del contribuyente.
>
> Siguen párrafos sobre "licencia de patente", "dependencia consciente" en licencias de patentes, extensión automática de licencias, y prohibición de licencias discriminatorias.
>
> Una licencia de patente es "discriminatoria" si no incluye dentro de su ámbito de cobertura, prohíbe el ejercicio de, o está condicionada al no ejercicio de uno o más de los derechos específicamente otorgados bajo esta Licencia. No puedes transmitir una obra cubierta si eres parte de un arreglo con un tercero que está en el negocio de distribuir software, bajo el cual haces pago al tercero basado en la extensión de tu actividad de transmitir la obra, y bajo el cual el tercero otorga, a cualquiera de las partes que recibirían la obra cubierta de ti, una licencia de patente discriminatoria (a) en conexión con copias de la obra cubierta transmitidas por ti (o copias hechas de esas copias), o (b) principalmente para y en conexión con productos específicos o compilaciones que contienen la obra cubierta, a menos que entraras en ese arreglo, o que esa licencia de patente fuera otorgada, antes del 28 de marzo de 2007.
>
> Nada en esta Licencia se interpretará como excluyendo o limitando cualquier licencia implícita u otras defensas contra infracción que de otra manera pudieran estar disponibles para ti bajo la ley de patentes aplicable.

**Explicación detallada:**
- **Concesión de licencia de patentes**: Todo contribuyente (quien añade código) concede automáticamente una licencia de sus "reclamaciones esenciales" (patentes que cubren el software tal como se distribuye). Es libre de regalías y global, abarcando uso, modificación y distribución. A diferencia de la GPLv2, que no mencionaba patentes de forma explícita, esto cierra lagunas donde un contribuyente podría demandar por sus propias patentes.
- **Dependencia consciente y extensión automática**: Si distribuyes software sabiendo que depende de una licencia de patente (por ejemplo, un acuerdo implícito), debes asegurar que la fuente esté disponible o extender la licencia a todos. Esto evita "trampas" donde las patentes se usan para forzar el cumplimiento.
- **Anti-discriminación**: Prohíbe arreglos donde se pagan regalías por distribución y el tercero concede licencias de patentes que restringen derechos GPL. La fecha de corte (28 de marzo de 2007) "abuela" acuerdos previos como el de Microsoft-Novell, pero impide nuevos. Esto fue una respuesta directa al acuerdo de 2006, como relata Fontana.
- **Ventajas y riesgos**: Las ventajas incluyen mayor protección contra "trolls de patentes" y el fomento de ecosistemas libres. Los riesgos, según informes como los de BearingPoint, radican en limitaciones para empresas a la hora de proteger su propiedad intelectual o monetizar vía patentes. En foros como Patents Stack Exchange, se debate que reduce demandas contra usuarios GPL, pero no impide patentar innovaciones nuevas.

## Comparación con la GPLv2

La GPLv2 carecía de cláusulas explícitas contra patentes, lo que dejaba vulnerabilidades. Por ejemplo, un contribuyente podía patentar partes del software y demandar a usuarios. La GPLv3 corrige esto con concesiones explícitas y mecanismos de retaliación, haciendo la licencia más resistente a patentes. Esto ha resultado en una adopción mixta: proyectos como el núcleo de Linux se mantuvieron en GPLv2 por compatibilidad, mientras que otros como Samba migraron a GPLv3.

## Implicaciones, Ejemplos y Controversias

**Implicaciones prácticas**:
- **Para desarrolladores**: Mayor seguridad al contribuir; sus patentes se comparten de manera automática.
- **Para empresas**: Favorece modelos de código abierto sin temor a demandas, pero exige precaución en el cumplimiento. Por ejemplo, Google usa GPLv3 en algunos proyectos, pero la evita en el núcleo de Android por cuestiones de compatibilidad.
- **Ejemplos**: El acuerdo Microsoft-Novell impulsó la cláusula anti-discriminación. En la década de 2010, disputas como Oracle contra Google (sobre APIs de Java) ilustraron cómo las patentes afectan al código abierto, aunque no directamente a GPL.

**Controversias**:
- Algunos critican su complejidad: LWN.net apuntó que la retaliación no es "total" y podría no disuadir a todos.
- Empresas temen que, si las demandan por patentes en código GPLv3, no puedan reconciliar con sus obligaciones (según Black Duck Blog).
- Aun así, sus contribuciones perduran, influyendo en licencias como MPL 2.0, con periodos de gracia para violaciones.

## Conclusión

Las cláusulas contra patentes en la GPLv3 suponen un paso estratégico para salvaguardar el software libre en un mundo plagado de patentes. Al forzar el reparto equitativo y desincentivar agresiones, fortalecen el copyleft y estimulan la innovación colaborativa. Aunque añaden algo de complejidad, su impacto ha sido positivo, mitigando riesgos y adaptándose a desafíos actuales. Para más información, consulta el texto oficial en gnu.org. S

## Referencias que Apoyan el Contenido

Estas fuentes respaldan las ventajas y la necesidad de las cláusulas contra patentes en la GPLv3, destacando su rol en la protección del software libre.

- [Free Software Foundation Europe (FSFE). "Patents and GPLv3" 🟡③🌐](https://fsfe.org/activities/gplv3/patents-and-gplv3.en.html). Este documento explica cómo las cláusulas abordan las amenazas de patentes.
- [BearingPoint. "Understanding GPL v3: Risks, benefits, and compliance" 🟡③🌐](https://bearingpoint.services/foss/en/newsblogs/dont-be-afraid-of-gplv3/) .- Analiza los beneficios de las provisiones de patentes para empresas.
- [FOSSA. "Open Source Software Licenses 101: GPL v3" 🟡③🌐](https://fossa.com/blog/open-source-software-licenses-101-gpl-v3/) .- Resalta la concesión explícita de derechos de patentes como una mejora clave.
- [PatentPC. "Understanding the Patent Provisions in Popular Open Source Licenses" 🟡③🌐](https://patentpc.com/blog/understanding-the-patent-provisions-in-popular-open-source-licenses) .-Enfatiza el rol protector de la cláusula de retaliación.
- [Vídeo: Richard Stallman. "Welcome to GPLv3" 🟡③🌐](https://www.youtube.com/watch?v=WNknNScP0tg) .- Stallman defiende el propósito de las cláusulas contra patentes.

## Referencias que Refutan el Contenido

Estas fuentes critican las cláusulas, argumentando que limitan la innovación empresarial, complican la adopción o no son tan efectivas como se afirma.

- [Black Duck (Synopsys). "Who's Afraid of GPL3? All About GPL Version 3" 🟡③🌐](https://www.blackduck.com/blog/whos-afraid-gpl3.html) .- Señala que las cláusulas de patentes pueden asustar a contribuyentes y limitar la monetización.
- [Klara Systems. "GPL 3: The Controversial Licensing Model and Potential Solutions" 🟡③🌐](https://klarasystems.com/articles/gpl-3-the-controversial-licensing-model-and-potential-solutions/) .- Critica las provisiones por riesgos legales y limitaciones en la distribución.
- [LWN.net. "GPLv3: a first look"](https://lwn.net/Articles/167825/) .- Apunta que la cláusula de retaliación no es tan fuerte como parece.
- [Phys.org. "Controversy Swirls Around Changes in GPLv3" 🟡③🌐](https://phys.org/news/2007-03-controversy-swirls-gplv3.html) .- Discute preocupaciones sobre cómo preserva derechos de patentes no GPL.
- [Vídeo: Linus Torvalds. "Linus Torvalds says GPL v3 violates everything that GPLv2 stood for" 🟡③🌐](https://www.youtube.com/watch?v=PaKIZ7gJlRU)

![[Plantilla - 1MT#One More Thing]]