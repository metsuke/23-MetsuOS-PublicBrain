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
created: 2025-10-09T06:17:58.164Z
modified: 2025-10-14T12:12:15.738Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: PatronesCalidadSoftware.mp4
---
# Curso sobre Patrones y Calidad del Software 🔴②

![Curso Patrones y Calidad del Softwarre](PublicBrain/_resources/21f22e00084c6932dd97ea0d27c492d4_MD5.jpg)

[[KB]]

> WIP Validando contenido y fuentes

En este curso trataremos las cuestiones relacionadas con patrones de diseño y calidad del software. Comenzaremos con las bases e iremos avanzando hacia una serie de prompts de contexto que nos sirvan en nuestro desarrollo en el dia a dia.

## Módulo 1: Introducción a los Patrones y la Calidad de Software

El objetivo principal aquí es sentar las bases, explicando por qué surgen los patrones y cómo se relacionan con la calidad del software. Es como el punto de partida para que todo el mundo entienda el "porqué" antes de entrar en detalles técnicos.

### Unidad 1.1: Conceptos Básicos de Patrones de Software
Definimos un patrón como una solución probada y reutilizable para problemas comunes en el diseño de software. Hablamos de su historia, desde las ideas de Christopher Alexander en arquitectura hasta su adaptación al software por el "Gang of Four" (GoF). Clasificamos los patrones en tipos: de diseño, arquitectónicos, idiomáticos y, por supuesto, los antipatrones (esos errores que todos cometemos alguna vez). Por ejemplo, comparamos el patrón Singleton con el antipatrón "God Object", que puede convertir tu código en un lío ingobernable.

### Unidad 1.2: Fundamentos de la Calidad de Software
Exploramos los atributos clave de calidad según el estándar ISO 25010, como la funcionalidad, el rendimiento, la compatibilidad, la usabilidad, la fiabilidad, la seguridad, la mantenibilidad y la portabilidad. También vemos métricas prácticas, como la complejidad ciclomática, el acoplamiento, la cohesión, las líneas de código (LOC) o la deuda técnica. Tocamos modelos como CMMI o la evolución de ISO/IEC 9126.

### Unidad 1.3: La Relación entre Patrones y Calidad
Aquí conectamos los puntos: cómo los patrones ayudan a mejorar la calidad al reducir la complejidad y promover principios como SOLID (responsabilidad única, abierto-cerrado, etc.). Analizamos casos reales, como la refactorización de sistemas legacy donde un patrón bien aplicado salva el día.

**Actividades sugeridas**: Una discusión en foro sobre un antipatrón que hayas visto en tu experiencia; lectura inicial de los capítulos 1-2 del libro del GoF o secciones de "Clean Code" de Robert C. Martin.

## Módulo 2: Patrones de Diseño Creacionales

En este módulo nos centramos en patrones que facilitan la creación de objetos, evaluando cómo impactan en la flexibilidad y reutilización del código. Es ideal para entender cómo evitar código rígido desde el principio.

### Unidad 2.1: Singleton y Factory Method
El Singleton asegura una única instancia de una clase, con pros y contras (por ejemplo, problemas en entornos multihilo). El Factory Method abstrae la creación de objetos, con ejemplos en lenguajes como Java o C#. En términos de calidad, estos patrones centralizan la lógica y mejoran la mantenibilidad.

### Unidad 2.2: Abstract Factory y Builder
Abstract Factory para familias de objetos relacionados, y Builder para construir objetos complejos paso a paso (piensa en interfaces fluidas). Ayudan a reducir el acoplamiento y simplifican las métricas de complejidad.

### Unidad 2.3: Prototype y Otros Patrones Creacionales
Prototype para clonar objetos y optimizar eficiencia. Analizamos su efecto en el rendimiento y el uso de memoria.

**Actividades sugeridas**: Implementa un Factory en tu lenguaje favorito y compara la deuda técnica antes y después. Lecturas: Capítulos 3-5 del GoF o "Head First Design Patterns" para ejemplos visuales y divertidos.

## Módulo 3: Patrones de Diseño Estructurales

Aquí hablamos de cómo componer clases y objetos para lograr escalabilidad y fácil mantenimiento. Son patrones que ayudan a que tu código crezca sin romperse.

### Unidad 3.1: Adapter y Bridge
Adapter para interfaces incompatibles, y Bridge para separar abstracción de implementación. Mejoran la portabilidad y la extensibilidad.

### Unidad 3.2: Composite y Decorator
Composite trata estructuras como árboles de forma uniforme, y Decorator añade responsabilidades dinámicamente. Promueven el principio abierto-cerrado y una buena cohesión.

### Unidad 3.3: Facade, Flyweight y Proxy
Facade simplifica subsistemas complejos, Flyweight optimiza memoria con objetos compartidos, y Proxy controla accesos (como carga perezosa). Impactan positivamente en rendimiento y seguridad.

**Actividades sugeridas**: Refactoriza un código antiguo usando Adapter y evalúa métricas con herramientas como SonarQube. Lecturas: Capítulos 6-8 del GoF o "Refactoring" de Martin Fowler.

## Módulo 4: Patrones de Diseño Comportamentales

Nos adentramos en patrones para la comunicación entre objetos, con énfasis en fiabilidad y usabilidad. Estos son geniales para sistemas dinámicos.

### Unidad 4.1: Chain of Responsibility y Command
Chain pasa solicitudes por una cadena, y Command encapsula solicitudes como objetos (útil para undo/redo). Aumentan la flexibilidad y facilitan las pruebas.

### Unidad 4.2: Iterator, Mediator y Memento
Iterator para acceso secuencial sin exponer estructuras, Mediator para centralizar comunicaciones complejas, y Memento para capturar estados. Reducen acoplamiento y mejoran fiabilidad.

### Unidad 4.3: Observer, State, Strategy, Template Method y Visitor
Observer para notificaciones (estilo pub/sub), State para comportamientos por estado, Strategy para algoritmos intercambiables, Template Method para algoritmos con pasos variables, y Visitor para operaciones sin modificar estructuras. Enfocados en usabilidad y mantenibilidad.

**Actividades sugeridas**: Crea un sistema de notificaciones con Observer y haz pruebas unitarias para medir cobertura. Lecturas: Capítulos 9-11 del GoF o "Patterns of Enterprise Application Architecture" de Fowler.

## Módulo 5: Patrones Arquitectónicos y de Integración

Ampliamos a patrones a nivel de sistema entero, evaluando calidad en escalabilidad y rendimiento. Perfecto para proyectos grandes.

### Unidad 5.1: MVC, MVP y MVVM
Model-View-Controller y sus variantes. Separan preocupaciones para una mejor mantenibilidad.

### Unidad 5.2: Microservices, Layered Architecture y Event-Driven
Microservices para servicios independientes, Layered para capas (presentación, negocio, datos), y Event-Driven para comunicaciones asíncronas. Métricas de escalabilidad y manejo de fallos.

### Unidad 5.3: Repository, Unit of Work y CQRS
Patrones de persistencia y segregación de comandos/consultas. Optimizan rendimiento y consistencia.

**Actividades sugeridas**: Diseña una arquitectura de microservices y simula cargas para medir calidad. Lecturas: "Building Microservices" de Sam Newman o "Domain-Driven Design" de Eric Evans.

## Módulo 6: Calidad de Software Avanzada y Herramientas

Profundizamos en prácticas y herramientas para integrar patrones con calidad real.

### Unidad 6.1: Métricas y Análisis de Calidad
Herramientas como SonarQube, Checkstyle o PMD. Análisis estático/dinámico, olores de código y refactorización.

### Unidad 6.2: Pruebas y Aseguramiento de Calidad
Tipos de pruebas (unitarias, integración, sistema) y enfoques como TDD/BDD. Integración con patrones, como mocks en Strategy.

### Unidad 6.3: DevOps y Calidad Continua
CI/CD, monitoreo (Prometheus, ELK Stack). Calidad en metodologías ágiles: revisiones de código, programación en pares.

**Actividades sugeridas**: Proyecto grupal aplicando patrones en una app y midiendo calidad. Lecturas: "Continuous Delivery" de Jez Humble o "The DevOps Handbook".

## Módulo 7: Temas Avanzados, Casos de Estudio y Proyecto Final

Aplicamos todo de forma integrada y exploramos tendencias actuales.

### Unidad 7.1: Antipatrones y Mejores Prácticas
Identificamos y corregimos antipatrones comunes, como el "Spaghetti Code".

### Unidad 7.2: Patrones en Contextos Modernos
Patrones cloud-native, en IA/ML o de seguridad (como Zero Trust). Calidad en software distribuido: resiliencia y observabilidad.

### Unidad 7.3: Casos de Estudio Reales
Análisis de proyectos open-source, como Spring Framework o Netflix OSS.

**Proyecto Final**: Desarrolla un sistema aplicando al menos cinco patrones, con informe de calidad (métricas, pruebas). Actividades: Presentaciones y revisiones entre pares. Lecturas: "Release It!" de Michael T. Nygård o artículos recientes de IEEE Software.

**Evaluación General**: 30% exámenes teóricos, 40% proyectos prácticos, 20% actividades y 10% participación.  
**Requisitos Previos**: Conocimientos básicos de programación orientada a objetos (por ejemplo, en Java o Python) y desarrollo de software.  
**Recursos Adicionales**: GitHub para ejemplos prácticos, o plataformas como Coursera para vídeos complementarios. Esta estructura es flexible y se puede ajustar al nivel de los participantes.

## Referencias Bibliográficas que Apoyan el Contenido

> WIP Validando Fuentes

Estas referencias respaldan los conceptos de patrones de diseño y calidad de software, promoviendo su uso para mejorar la mantenibilidad y eficiencia. He verificado su existencia y vigencia actual (a fecha de octubre de 2025), priorizando enlaces oficiales o de editores.

- [Gamma, E., Helm, R., Johnson, R., & Vlissides, J. (1994). Design Patterns: Elements of Reusable Object-Oriented Software 🌐🟡③](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612) Addison-Wesley. .
- Martin, R. C. (2008). *Clean Code: A Handbook of Agile Software Craftsmanship*. Prentice Hall. Enlace: [https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) (versión corregida y vigente).
- Freeman, E., Robson, E., Bates, B., & Sierra, K. (2004). *Head First Design Patterns*. O'Reilly Media. Enlace: [https://www.oreilly.com/library/view/head-first-design/9781492077992/](https://www.oreilly.com/library/view/head-first-design/9781492077992/).
- Fowler, M. (1999). *Refactoring: Improving the Design of Existing Code*. Addison-Wesley. Enlace: [https://www.amazon.com/Refactoring-Improving-Design-Existing-Code/dp/0201485672](https://www.amazon.com/Refactoring-Improving-Design-Existing-Code/dp/0201485672).
- Fowler, M. (2002). *Patterns of Enterprise Application Architecture*. Addison-Wesley. Enlace: [https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420).
- Newman, S. (2015). *Building Microservices: Designing Fine-Grained Systems*. O'Reilly Media. Enlace: [https://www.oreilly.com/library/view/building-microservices/9781491950340/](https://www.oreilly.com/library/view/building-microservices/9781491950340/).
- Evans, E. (2003). *Domain-Driven Design: Tackling Complexity in the Heart of Software*. Addison-Wesley. Enlace: [https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215).
- Humble, J., & Farley, D. (2010). *Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation*. Addison-Wesley. Enlace: [https://www.oreilly.com/library/view/continuous-delivery-reliable/9780321670250/](https://www.oreilly.com/library/view/continuous-delivery-reliable/9780321670250/).
- Kim, G., Humble, J., Debois, P., & Willis, J. (2016). *The DevOps Handbook: How to Create World-Class Agility, Reliability, and Security in Technology Organizations*. IT Revolution Press. Enlace: [https://itrevolution.com/product/the-devops-handbook-second-edition/](https://itrevolution.com/product/the-devops-handbook-second-edition/) (edición actualizada).
- Nygård, M. T. (2018). *Release It!: Design and Deploy Production-Ready Software* (2ª ed.). Pragmatic Bookshelf. Enlace: [https://pragprog.com/titles/mnee2/release-it-second-edition/](https://pragprog.com/titles/mnee2/release-it-second-edition/).
- ISO/IEC 25010:2011. *Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models*. Enlace: [https://www.iso.org/standard/35733.html](https://www.iso.org/standard/35733.html).
- Artículo: "Software Design Patterns and Architecture Patterns – A Study Explored" (2023). IEEE Xplore. Enlace: [https://ieeexplore.ieee.org/document/10073279/](https://ieeexplore.ieee.org/document/10073279/).
- Vídeo: "Strategy Pattern - Design Patterns - Programming in Spanish" (2025). Canal: Programación en español. Enlace: [https://www.youtube.com/watch?v=j0I_hzEhfTE](https://www.youtube.com/watch?v=j0I_hzEhfTE).

## Referencias Bibliográficas que Refutan el Contenido

> WIP Validando Fuentes

Estas fuentes critican aspectos como el abuso de patrones, argumentando que pueden añadir complejidad innecesaria, ralentizar el desarrollo o no ser siempre óptimos. He comprobado su validez y actualidad, enfocándome en críticas científicas o prácticas reales.

- Artículo: "Criticism of patterns" (vigente en 2025). Refactoring.Guru. Enlace: [https://refactoring.guru/design-patterns/criticism](https://refactoring.guru/design-patterns/criticism) (critica soluciones ineficientes y dogmatismo).
- Artículo: "Rethinking Design Patterns" (2007, aún relevante). Coding Horror. Enlace: [https://blog.codinghorror.com/rethinking-design-patterns/](https://blog.codinghorror.com/rethinking-design-patterns/) (advierte contra la complejidad añadida).
- Wiki: "Design Patterns Considered Harmful" (vigente). C2 Wiki. Enlace: [https://wiki.c2.com/?DesignPatternsConsideredHarmful](https://wiki.c2.com/?DesignPatternsConsideredHarmful) (discute flexibilidad excesiva y dificultad de mantenimiento).
- Artículo: "Why Most Design Patterns Are Overused and Misunderstood" (2024). LinkedIn. Enlace: [https://www.linkedin.com/pulse/why-most-design-patterns-overused-misunderstood-carlos-santana-rold%C3%A1n-txscf](https://www.linkedin.com/pulse/why-most-design-patterns-overused-misunderstood-carlos-santana-rold%C3%A1n-txscf) (habla de optimización prematura).
- Artículo: "Design patterns feel completely obsolete now" (2018, discusión vigente). Hacker News. Enlace: [https://news.ycombinator.com/item?id=16351750](https://news.ycombinator.com/item?id=16351750) (critica su obsolescencia con lenguajes funcionales).
- Artículo: "Our Over Obsession With Patterns" (vigente). Dan Goslen Blog. Enlace: [https://dangoslen.me/blog/our-obsession-with-patterns/](https://dangoslen.me/blog/our-obsession-with-patterns/) (advierte contra el uso excesivo como solución universal).
- Artículo: "Shortcomings of ISO 25010" (vigente). arc42 Quality Model. Enlace: [https://quality.arc42.org/articles/iso-25010-shortcomings](https://quality.arc42.org/articles/iso-25010-shortcomings) (critica la falta de pragmatismo en modelos de calidad como ISO 25010).


![[Plantilla - 1MT#One More Thing]]