---
iaStatus: 8
iaStatus_Model: Grok-3, Raúl Carrillo aka Metsuke
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-05-30T21:34:27.819Z
modified: 2025-06-01T19:05:00.813Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: 
nav_secondary: 
tags:
---
# Blog - Sobre el sistema de validacion de contenido de MetsuOS - 2025-06-01 🔴②

![El Barco en la caja que todos compartimos](PublicBrain/_resources/f00ec31c58f11d200bcc9544eb02858e_MD5.jpeg)

[[PublicBrain/PublicIndex/Index|Index]]

## Introducción

Inspirado por el trabajo de [@dvargaspardo 🌐](https://x.com/dvargaspardo) y el documental en preparación que anunció en el canal de [@tbrazil_speccy 🌐](https://x.com/tbrazil_speccy). he decidido compartir con el público generalista los fundamentos del sistema de validación de contenido de mi proyecto, MetsuOS. Este sistema, representado por las icónicas "pelotillas de colores" ([[⚫🔴🟡🟢🔵⚪ (🔴②)]]), no solo se aplica al desarrollo de videojuegos, sino que aborda una problemática más amplia: la gestión del conocimiento en un mundo saturado de información no necesariamente fidedigna.

## La problemática: deuda técnica y validación del conocimiento

A lo largo de mi experiencia como programador, emprendedor y redactando documentación técnica he identificado un problema recurrente: la **deuda técnica**. Este término, comúnmente asociado al desarrollo de software, se refiere a la acumulación de soluciones temporales que se posponen para "arreglar más tarde", pero que raramente se resuelven. Sin embargo, esta deuda no es exclusiva del ámbito tecnológico; se manifiesta en múltiples disciplinas, incluida la ciencia.

En el ámbito científico, la "deuda técnica" se traduce en la dificultad para verificar la validez de un volumen creciente de publicaciones académicas. La proliferación de artículos de dudosa calidad, a menudo impulsada por intereses económicos o académicos, dificulta la identificación de investigaciones fiables. Además, cuando surge nueva evidencia, no existe un sistema eficiente para "recalcular" el conocimiento acumulado, lo que frena el avance científico. Esta problemática me llevó a replantear la metodología para gestionar y validar el conocimiento.

## El sistema de MetsuOS: un enfoque híbrido

Inicialmente, mi intención fue crear un sistema manual basado en una **álgebra de la certeza**, donde nuevas evidencias recalcularan los porcentajes de fiabilidad de los razonamientos previos. Este enfoque, inspirado en sistemas expertos, pretendía servir como base para avanzar en inteligencia artificial (IA). Sin embargo, el auge de los modelos de lenguaje de gran escala (LLM, por sus siglas en inglés), como los que ofrecen capacidades de autocompletado avanzado, me obligó a replantear la estrategia.

En lugar de construir el sistema desde cero, opté por integrar los LLM con el trabajo humano en un proceso por fases, representado por las "pelotillas de colores":

1.  **Fase inicial**: Utilizo varios modelos de IA, como los de Google o ChatGPT, para generar una base de conocimiento sobre un tema. Cruzo los textos generados por diferentes modelos para identificar inconsistencias y refinar el contenido. En esta etapa, se recopilan fuentes bibliográficas iniciales.
2.  **Curación humana**: Leo libros, consulto fuentes primarias y verifico la validez de las referencias. Este paso asegura que el contenido sea preciso y esté correctamente referenciado.
3.  **Validación científica**: Desarrollo procesos para validar el contenido con rigor académico, aunque esta fase aún está en construcción.
4.  **Automatización**: Implemento automatizaciones (bajo el paraguas de #MetsuOS) para afinar el conocimiento y prepararlo para su uso en sistemas híbridos.
5. **Entrenamiento híbrido**: Combino LLMs con sistemas expertos para entrenar modelos que actúen como coprocesadores controlados por humanos, no como sustitutos.
6. **Aplicaciones prácticas**: Aplico este conocimiento validado al desarrollo de videojuegos y otras áreas, siempre bajo supervisión humana.
    
Este enfoque híbrido busca aprovechar lo mejor de ambos mundos: la capacidad de procesamiento de los LLMs y el juicio crítico humano, minimizando las invenciones o "alucinaciones" de los modelos automáticos.
## PublicBrain y el repositorio GIT

El sistema de validación de contenido está integrado en la sección **PublicBrain** de mi proyecto, que cuenta con un repositorio GIT paralelo. Este repositorio permite gestionar y automatizar el conocimiento, facilitando su actualización y reprocesamiento en función de nuevas evidencias. El objetivo final es crear una base de conocimiento universal y dinámica que sirva para entrenar sistemas híbridos entre LLMs y sistemas expertos, aplicables a campos como el desarrollo de videojuegos, la investigación científica o la toma de decisiones estratégicas.

## Por qué no confiar únicamente en los LLMs

Existen razones geoestratégicas y prácticas que me llevan a no depender exclusivamente de los LLMs. Por un lado, la falta de control sobre los datos y los algoritmos de terceros plantea riesgos para la privacidad y la seguridad. Por otro, los LLMs, aunque potentes, no son infalibles y requieren supervisión humana para garantizar la fiabilidad del conocimiento generado. Mi enfoque, inspirado en la filosofía de Adama en _Battlestar Galactica_ —quien evitaba las redes globales para proteger a la humanidad—, prioriza el control humano sobre la tecnología.

## Conclusión

El sistema de validación de contenido de MetsuOS es un intento de abordar la deuda técnica y la saturación de información en la era de los LLMs. Al combinar la potencia de la IA con la curación humana, busco crear una base de conocimiento dinámica y fiable que apoye a los humanos como un coprocesador, no como un reemplazo. Este enfoque, aunque aún en desarrollo, tiene el potencial de transformar la forma en que gestionamos el conocimiento en disciplinas tan diversas como la ciencia, los videojuegos y los negocios.

## Referencias bibliográficas

### Fuentes que apoyan el enfoque

1. **Russell, S., & Norvig, P. (2021). _Artificial Intelligence: A Modern Approach_ (4th ed.). Pearson.**
	- Este libro aborda la importancia de combinar sistemas expertos con técnicas de IA modernas, apoyando la idea de sistemas híbridos para la validación de conocimiento.
	- [Enlace del Libro en Amazon "A Modern Aproach"  🌐🟡③](https://www.amazon.com/Artificial-Intelligence-A-Modern-Approach/dp/0134610997)
        
2. **Goodfellow, I., Bengio, Y., & Courville, A. (2016). _Deep Learning_. MIT Press.**
      - Explica las limitaciones de los modelos de aprendizaje profundo, como los LLMs, y la necesidad de supervisión humana para garantizar resultados fiables.
      - [Enlace en MIT Press 🌐🟡③](https://mitpress.mit.edu/9780262035613/deep-learning/)
        
3. **Ioannidis, J. P. A. (2005). Why Most Published Research Findings Are False. _PLoS Medicine, 2_(8), e124.**
        - Este artículo destaca los problemas de calidad en las publicaciones científicas, apoyando la necesidad de sistemas de validación rigurosos.
        - [Enlace al PDF del artículo de Ioannidis 🌐🟡③](https://www.stat.cmu.edu/~ryantibs/journalclub/ioannidis.pdf)
        
### Fuentes que refutan o cuestionan el enfoque

1. **Halevy, A., Norvig, P., & Pereira, F. (2009). The Unreasonable Effectiveness of Data. _IEEE Intelligent Systems, 24_(2), 8-12.**
      - Este artículo defiende que los modelos basados únicamente en datos masivos (como los LLMs) pueden ser suficientes sin necesidad de sistemas expertos, lo que contradice la necesidad de enfoques híbridos.
      - [The Unreasonable Effectiveness of Data 🌐🟡③](https://doi.org/10.1109/MIS.2009.36)
        
2. **Marcus, G. (2018). Deep Learning: A Critical Appraisal. _arXiv preprint arXiv:1801.00631_.**
      - Cuestiona la capacidad de los sistemas híbridos para superar las limitaciones fundamentales de los LLMs, argumentando que los problemas de "alucinaciones" son inherentes a la tecnología actual.      
    - [Deep Learning: A Critical Appraisal 🌐🟡③](https://arxiv.org/abs/1801.00631)
        
3. **Smith, B. C. (2019). _The Promise of Artificial Intelligence: Reckoning and Judgment_. MIT Press.**    
    - Sugiere que la supervisión humana en sistemas de IA puede ser inviable a gran escala debido a los costos y la complejidad, lo que cuestiona la escalabilidad del enfoque híbrido propuesto.   
    - [The Promise of Artificial Intelligence: Reckoning and Judgment 🌐🟡③](https://www.amazon.es/Promise-Artificial-Intelligence-Reckoning-Judgment/dp/0262043041/ref=sr_1_1?__mk_es_ES=ÅMÅŽÕÑ&dib=eyJ2IjoiMSJ9.JucKMIf-q6m4S4THH_dNwVinRX-CxzJ78LRFcGnPZgpoMqYdXWG1o7aYcaAIJ72T4AEGVTDkny-sSUayL8rLv8PKlgOd6wY3cVs99FQRMX7dv4yjHzr8hw7baCHLZz4As0dwJ_EKwcJ6oHH7s-GdfrRvVz1uEJm8u3xEi6wWxRkjkdCk0jDca79fD1EiIaeG-kCNDu0vBNWl2DvGltkNYAixOHDua94sWvxuzMjdQfxp9Ze0kdkC12E3jhWwTpmvgyzj4YnFPUZtHM2MhDoZQLuZfC5ZB_odDhqsx391zmA._OnI0Exk7mEI4SyJs3C5Y4yXeKFe6cOXYGCAdEN7lng&dib_tag=se&keywords=The+Promise+of+Artificial+Intelligence&qid=1748805648&sr=8-1&ufe=app_do%3Aamzn1.fos.fde3827e-5b32-4544-acac-9bcf8407a6a6)

![[Plantilla - 1MT#One More Thing]]