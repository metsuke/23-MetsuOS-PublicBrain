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
created: 2025-09-30T10:16:07.557Z
modified: 2026-03-29T09:05:06.066Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 76
nav_primary:
nav_secondary:
tags:
MOS_TopImg_Video: MetsuOSBaseIcon.mp4
---
 
# Apps

![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)

[[PublicBrain/Index|Index]]



> WIP

Siguiendo la estela de [[El Proyecto|las patas de este proyecto]], enumero aquí aquí las apps que forman parte del toolkit que nos permitira, una vez en funcionamiento, la creación y mantenimiento de videojuegos accesibles que, en el fondo, es en buena medida de lo que va todo esto.

Organizo la estructura en capas al estilo cebolla crocante con ligeras trazas de vinagreta agridulce, para construir, mas que una "aplicación" un sistema cuyas partes puedan ser usadas como un conjunto cuyo resultado sea mayor que la suma de sus partes.

En cuanto a las capas de funcionamiento implicadas, cada aplicación, modulo y libreria del sistema pretendo tenga las siguientes versiones:

* FSF-Fan Layer .- Será la que tenga el código disponible en abierto, pero limitado a componentes compatibles con GNUv3. Si un componente no existe bajo GNUv3 la funcionalidad no será implementada en esta capa, pero ofrecera una guia clara para los Fans de GNUv3 de que cosas tienen que implementar si quieren ganar presencia y efectividad. Se usará licencias GNUv3 Compatibles.
* EFF-Fan Layer .- Dada la deriva privativa de GNUv3, en esta capa será la que tenga el código disponible en abierto, pero limitado a componentes compatibles con GNUv2. Si un componente no existe en v2 pero si en v3, se creará de ser posible una reimplementación con v2 y de no serlo, se usara el componente de v2 como aplicacion externa. Recordemos que las clausulas que contiene a priori no son compatibles con el antiintromisionismo, y que requiere una argumentación logica e irrefutable optar por implementar determinada opción unicamente en v3, como podrian llegar a ser usos abusivos o incorrectos de patentes de software.
* **Community** Layer .- Será la que tenga código disponble en abierto, y potencie al máximo lo que el software libre y de codigo abierto puede aportar. Usara componentes de la versión GFan si existe o implementará las que no, con licencia MIT o compatibles.
* **Pro** Layer - Se apoyará en la Community como si esta fuera una app, de modo que de aquí en adelante ya no hablamos de softrware libre ni de codigo abierto, sino de apps privadas y en el futuro comerciales mediante - probablemente - licencias. Esta capa tendrá por objetivo el uso de la versión Community pero adaptada a las necesidades, agilidad y robustez de un profesional.
* **Enterprise** Layer .- Estas versiones, tambien privadas, se apoyan en la pro, y tienen por objetivo llevar la gestión profesional al nivel de lo que una empresa de tamaño pequeño o medio, requiere, trabajando también - probablemente - con un sistema de licencias.

En algunos casos, [como propuse en este tweet con el conversor de imagenes 🌐](https://x.com/metsuke/status/1971099781633130801), es posible que proponga alguna forma de uso gratuito limitado de las versiones pro, a modo de prueba y como regalo a los que siguen el proyecto con atención, pero siempre como servicio sin acceso al código.

Este planteamiento está vivo, pero es algo que he reflexionado  bastante, ni quiero dejar en la estacada a los que colaboran con el software libre construyendo una base sólida que evita que los desarrolladores se enquisten en monopolios ni quiero someter el proyecto a la falta de profesionalidad real del desarrollo al estilo "do it yourself". En el equilibrio y la variedad de opciones, está el punto medio. Puedes ver más sobre esto en [[De Software Libre, Licencias y Filosofías en entornos VUCA 🟡③]]

## Utilidades temporales

Durante la fase intermedia entre mi sistema actual privado y la implementacion del primer MetsuOS público, estoy empezando a crear algunas herramientas de transicion que quiza puedan serte de utilidad a ti tambien. En este momento:

* [MetsuDiskSpaceViewer 🟡③🌐](https://github.com/metsuke/MetsuDiskSpaceViewer#metsudiskspaceviewer) .- Script de apoyo en el desarrollo de **MetsuOS** para analizar y visualizar dónde se consume el espacio en disco, especialmente en volúmenes externos.
## Herramientas de apoyo

Nada se construye sobre la nada (salvo, quizá, las partículas fundamentales de las que está hecho el universo físico).

De la misma forma, todo lo que hoy llamamos «mundo digital» —desde la computación más básica hasta los lenguajes de programación que sustentan MetsuOS— descansa sobre una serie de tecnologías y herramientas que no solo hacen posible su existencia, sino que permiten que siga creciendo día tras día.

Entre esas capas fundamentales y el código que forma el núcleo de nuestro sistema operativo se encuentran una serie de herramientas imprescindibles: son el andamiaje invisible que coordina, organiza y hace viable el resto del desarrollo. Lo que sigue es precisamente el mapa de ese andamiaje.


```mermaid
graph TD
    A[Desarrollo] --> B[Propio]
    A[Desarrollo] --> C[Otras]

    C --> D[Linux Kernel]
    C --> E[Python]
    C --> H[Poetry]

    E --> F[MetsuDepManager]
    H --> F[MetsuDepManager]
    B --> F[MetsuDepManager]

    F --> G[mosLib]
    B --> G[mosLib]

    D --> J[Debian GNU/Linux]
        
    J --> K[Parrot GNU/Linux Tools]
        
    E --> I[MetsuOS GNU/Linux]
    J --> I[MetsuOS GNU/Linux]
    K --> I[MetsuOS GNU/Linux]

    %% Relación opcional
    G -.-> I

    %% Estilos con colores de fuente explícitos
    classDef external fill:#4a5568,stroke:#2d3748,color:#e2e8f0
    classDef propio   fill:#2b6cb0,stroke:#2c5282,color:#ffffff
    classDef final    fill:#22543d,stroke:#276749,color:#ffffff

    class D,E,H,J,K external
    class B,F,G propio
    class I final
```

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```


![MetsuDepManager](PublicBrain/_resources/570f078529742a81c508c3b36eac5d26_MD5.jpg)
## MetsuDepManager – Gestor de Dependencias Ético para MetsuOS 🟡③

MetsuDepManager es un gestor de dependencias ético, seguro, accesible y listo para producción para Python, diseñado específicamente para entornos regulados como empresas con políticas de seguridad estrictas (banca, defensa, sanidad, administraciones públicas), entornos educativos obligados por normativas como la LOMLOE y el Real Decreto 1112/2018 de accesibilidad, sistemas air-gapped o con conexión restringida (industria, investigación clasificada), y proyectos sujetos a regulaciones como RGPD, NIS2, ENS Alto o Ciberseguridad Nacional. Como wrapper ligero sobre Poetry, que actúa como su motor principal, integra un motor de políticas avanzado que asegura cumplimiento normativo (vulnerabilidades, licencias, orígenes geográficos) sin comprometer la velocidad ni la usabilidad. Su enfoque offline-first y su soporte para SBOM (Software Bill of Materials) lo convierten en una herramienta indispensable para mitigar riesgos en la cadena de suministro de software, alineándose con regulaciones como NIS2, ENS Alto, DORA e ITAR/EAR.

Continuyar leyendo en ... [[MetsuDepManager - Visión general del proyecto 🟡③]] y [[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

 --- column-end ---
--- multi-column-end

## MetsuOS System Core

Este es el núcleo del sistema operativo, incluye el sistema operativo como tal sobre el que trabaja una libreria sobre la que se asientan el resto de elementos.  Esto permite que MetsuOS, a futuro, pueda correr tanto como sistema operativo nativo o como algo asentado sobre la versione de la mosLib correspondiente a nuestro sistema.

```mermaid
graph LR
    A[MetsuOS] --> B[mosLib]
    B --> C[mosSystemCore]
    C --> D[mosSystemUI]
```

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```

![MetsuOS Icon](_resources/44c1f46d745c51f385f88f004bec044a_MD5.jpg)

### MetsuOS: El Sistema Operativo que Libera tu Potencial

**MetsuOS** es más que un sistema operativo: es una plataforma innovadora basada en GNU/Linux, diseñada para integrarse perfectamente en cualquier entorno. Flexible, potente y adaptable, MetsuOS es la base ideal para ejecutar aplicaciones en diversos sistemas, desde Windows y macOS hasta otras distribuciones Linux.

En el corazón de MetsuOS está **mosLib**, una biblioteca robusta que asegura una experiencia fluida y eficiente, sin importar el sistema operativo subyacente. Con MetsuOS, automatizamos los procesos repetitivos, liberándote para que puedas enfocarte en lo que realmente importa: ser humano, crear y alcanzar tus metas.

**MetsuOS**: Automatización inteligente. Libertad para innovar.

 --- column-end ---

  ![mosLib Icon](_resources/4b08d9c1c1d378d5df3ac0dd6de347a0_MD5.jpg)
### mosLib: El Corazón de MetsuOS

**mosLib** es la biblioteca fundamental que impulsa **MetsuOS**, diseñada para ofrecer una ejecución fluida y versátil, ya sea de forma nativa o en cualquier sistema operativo o entorno, como Windows, macOS o distribuciones Linux.

Con **mosLib**, todos los módulos del sistema funcionan en armonía. Esta potente biblioteca unifica, gestiona y optimiza desde las funciones esenciales del entorno hasta características avanzadas de accesibilidad, garantizando estabilidad y rendimiento sin igual.

mosLib (y - a priori - todos los modulos y aplicaciones que funcionan por encima de este), serán - en primera instancia, desarrollados en Python. Es una decisión argumentada ([[¿Por qué Python es la elección ideal para desarrollar en el ecosistema completo de MetsuOS? 🟡③]]), aunque lejos del sistema absoluitamente dinamico y basado en [[Blog - Parece extremadamente probable que la verdad absoluta no exista - 2025-05-23 🔴②|decisiones probabilisticas deppendientes de contexto]] que persigo, sin embargo, es necesario empezar el sistema por algun lado y esta, me parece la mejor decisión en este momento ( 🔴②)

**mosLib**: La base sólida para un sistema sin límites.

Continuar leyendo en ... [[mosLib - El Corazón de MetsuOS  ⚫①]]

 --- column-end ---

![mosSystemCore Icon](_resources/a5420290de63dc025383f319be29ee2d_MD5.jpg)
### mosSystemCore: El Puente Unificador de MetsuOS

mosSystemCore es el bloque fundamental de código que actúa como adaptador inteligente entre mosLib y las particularidades de cada sistema operativo host. Toma las funciones universales de mosLib —diseñadas para una ejecución fluida y versátil— y las transforma, integrando las especificidades nativas de entornos como GNU/Linux, Windows, macOS u otras distribuciones, para generar un corpus único de funcionalidades unificadas. De esta manera, mosSystemCore asegura que el ecosistema de MetsuOS opere de forma homogénea y eficiente, independientemente del sustrato subyacente, eliminando fricciones y maximizando la compatibilidad.

Este núcleo no solo traduce y optimiza llamadas a APIs, manejo de recursos y dependencias del host, sino que también incorpora capas de abstracción para accesibilidad, automatización y seguridad, permitiendo que el resto de módulos —como mosSystemUI o mosAppManager— funcionen sin interrupciones. 

*mosSystemCore : Unificación sin fronteras. Eficiencia en cualquier entorno.*

 --- column-end ---

![mosSystemUI](_resources/ff83acc613b0ecaf57d45bf283768012_MD5.jpg)
### mosSystemUI: La Interfaz que Conecta tu Visión con la Realidad

**(codename: PyTuxUI) **

mosSystemUI es el lienzo vivo de MetsuOS, una interfaz de usuario intuitiva y adaptable que transforma la complejidad subyacente del sistema en una experiencia visual y táctil accesible para todos. Construida sobre las bases sólidas de mosSystemCore, esta capa proporciona elementos de UI unificados —como paneles dinámicos, menús contextuales y dashboards personalizables— que se renderizan de manera consistente en cualquier entorno host, desde entornos nativos GNU/Linux hasta aplicaciones en Windows o macOS.

Con mosSystemUI, la accesibilidad no es un añadido, sino el núcleo: integra herramientas como lectores de pantalla integrados, navegación por gestos y modos de alto contraste que se adaptan automáticamente al usuario, garantizando que creadores de videojuegos y jugadores por igual puedan interactuar sin barreras. Desde la gestión de tareas hasta la supervisión de automatizaciones, mosSystemUI orquesta la armonía entre el usuario y el sistema, haciendo que lo abstracto sea tangible y lo técnico, humano.

mosSystemUI: Interfaz sin límites. Donde la accesibilidad encuentra la innovación.

 --- column-end ---
--- multi-column-end

## MetsuOS Base System: El Pilar Accesible de la Interfaz Unificada

MetsuOS Base System es la base estructural y accesible que se edifica directamente sobre mosSystemUI, integrando una capa intermedia de módulos clave como mosA11YManager, mosAutomationManager, mosBrainManager, mosIAManager, mosLegalManager, mosNetManager, mosRTManager, mosSecurityManager, y mosTaskManager en un núcleo cohesivo y dinámico. 

Este sistema fundamental transforma la interfaz intuitiva de mosSystemUI en un puente hacia la inclusión, asegurando una verificación constante de accesibilidad a través de herramientas como mosA11YTool, automatizando procesos repetitivos con mosAutomationManager, reforzando la seguridad con mosSecurityManager, gestionando tareas con precisión mediante mosTaskManager, y facilitando un ecosistema de aplicaciones coordinado por mosAppEcosystem, que integra herramientas como mosGameTool para mosGameMaker y mosRetroLauncher en cualquier entorno. 

En el corazón de MetsuOS, Base System encarna la esencia de un sistema sin barreras, donde la accesibilidad impulsa la innovación y convierte la complejidad técnica en un espacio humano de empoderamiento para creadores y usuarios.

Los módulos Manager integran funcionalidad y configuración, y mediante mosBrainManager aplican la metodología de validación de contenidos de MetsuOS, persiguiendo el máximo rigor científico con un enfoque adaptativo que evalúa credibilidad y solidez, mientras neutralizan dogmas "científicos", religiosos e ideológicos, buscando ofrecer al usuario información validada, neutral y contextualizada.

MetsuOS Base System: Accesibilidad ilimitada. Innovación sin fronteras.

```mermaid
graph LR
	D[mosSystemUI]
    D --> E[mosA11YManager]
    D --> F[mosAutomationManager]
    D --> G[mosBrainManager]
    D --> H[mosIAManager]
    D --> I[mosLegalManager]
    D --> J[mosNetManager]
    D --> K[mosRTManager]
    D --> L[mosSecurityManager]
    D --> M[mosTaskManager]
```


--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```

### mosA11YManager

![mosA11YManager Icon](_resources/bda47e38a2ead5db4a84c7244f2daa19_MD5.jpg)

**mosA11YManager: El Guardián de la Accesibilidad Universal en MetsuOS**

mosA11YManager es el módulo central que orquesta la accesibilidad en todo el ecosistema MetsuOS, integrándose directamente con mosSystemUI y herramientas como mosA11YTool para garantizar que cada interacción sea inclusiva por diseño. Este gestor verifica en tiempo real el cumplimiento de estándares como WCAG, implementa lectores de pantalla avanzados, navegación por voz y gestos, y adapta dinámicamente la interfaz a necesidades individuales —desde modos de alto contraste hasta soporte para discapacidades motoras o cognitivas—.

Más allá de la corrección, mosA11YManager impulsa la creación de videojuegos accesibles mediante mosGameMaker, auditando assets en mosImageConverter y entornos en mosRetroLauncher. Con mosBrainManager, evalúa la usabilidad con rigor probabilístico, neutralizando barreras y fomentando la innovación inclusiva.

mosA11YManager: Accesibilidad como superpoder. Inclusión sin excepciones.

--- column-end --- 
### mosAutomationManager

![mosAutomationManager Icon](_resources/83fd343711cede49e619f2d0f2e51bb1_MD5.jpg)

**mosAutomationManager: La Orquestadora de Procesos Inteligentes en MetsuOS**

mosAutomationManager es el motor de automatización que libera al usuario de tareas repetitivas, construyendo flujos inteligentes sobre mosSystemUI para optimizar el desarrollo y mantenimiento de videojuegos accesibles. Integra scripts personalizables, macros contextuales y workflows que se activan por eventos —desde compilación automática en mosGameMaker hasta sincronización en mosGitSync—.

Apoyado en mosTaskManager para priorización y mosSecurityManager para ejecución segura, este módulo transforma rutinas en eficiencia, permitiendo enfocarte en la creatividad. En versiones Pro y Enterprise, añade IA predictiva para anticipar necesidades y escalar operaciones en equipos.

mosAutomationManager: Automatiza lo mundano. Libera lo extraordinario.

--- column-end --- 
### mosBrainManager

![mosBrainManager Icon](_resources/39b789fabb79e6f970ad5e0bb5621d16_MD5.jpg)

**mosBrainManager: El Validador de Sabiduría Contextual en MetsuOS**

mosBrainManager es el núcleo cognitivo que aplica el sistema de niveles de validación ⚫🔴🟡🟢🔵⚪ en todos los contenidos y procesos de MetsuOS, asegurando información neutral, rigurosa y libre de dogmas. Integrado con mosSystemUI, evalúa credibilidad probabilística —combinando análisis científico, filosófico y empático— para etiquetar datos en herramientas como mosBrainTool o mosIAPromtManager.

Neutraliza sesgos ideológicos o "opiniones expertas" anticientíficas, incorporando el estándar OTAN de fiabilidad (A-F / 1-6) y referencias cruzadas. En el ecosistema de apps, guía la creación de juegos con conocimiento consolidado, promoviendo decisiones informadas y éticas.

mosBrainManager: Sabiduría probabilística. Conocimiento sin cadenas.

--- column-end --- 
### mosIAManager


![mosIAManager Icon](_resources/bba8e48326660cc4ba09df8bbbbfe8b7_MD5.jpg)
**mosIAManager: El Orquestador de Ejecución IA en MetsuOS**

mosIAManager es el gestor central de ejecución de inteligencia artificial que coordina, optimiza y supervisa todos los procesos IA dentro del ecosistema MetsuOS, asentado sobre mosSystemUI. Controla la carga, priorización y escalado de modelos —desde inferencia local hasta integración con servicios externos— en herramientas como mosIAPromtManager, mosBrainTool o mosGameMaker para generación accesible de assets, diálogos o mecánicas.

Integra con mosTaskManager para colas inteligentes, mosSecurityManager para ejecución en sandbox y mosBrainManager para validación probabilística de salidas IA. En versiones Pro y Enterprise, habilita pipelines personalizados, fine-tuning seguro y despliegue multi-GPU/TPU, manteniendo la soberanía del usuario sobre datos y modelos.

mosIAManager: Ejecución IA sin límites. Inteligencia al servicio de la creación.

--- column-end ---
### mosLegalManager

![mosLegalManager Icon](_resources/ad04c83625a745165fa86b6485f0ac52_MD5.jpg)

**mosLegalManager: El Escudo de Cumplimiento Normativo en MetsuOS**

mosLegalManager es el módulo que asegura el cumplimiento legal y ético en todo el sistema, verificando licencias, derechos de autor y regulaciones —como GDPR o accesibilidad— sobre mosSystemUI. Integra con mosAppEcosystem para auditar assets, contratos o distribuciones.

Apoyado en mosBrainManager para análisis probabilístico de riesgos legales, genera reportes automáticos y alertas. En versiones Enterprise, gestiona licencias comerciales y auditorías para PYMEs, manteniendo el equilibrio entre software libre (Community) y privado.

mosLegalManager: Legalidad proactiva. Innovación con integridad.

--- column-end --- 
### mosNetManager

![mosNetManager Icon](_resources/461fe69c35a8db236a5087f5a5ec08ba_MD5.jpg)

**mosNetManager: El Conector Universal de Redes en MetsuOS**

mosNetManager es el gestor de conectividad que unifica redes locales, cloud y P2P en MetsuOS, asegurando comunicación fluida y segura sobre mosSystemUI. Maneja protocolos adaptativos —WebRTC, VPN integradas y offline-first— para sincronización en mosGitSync, multiplayer en mosGameMaker o actualizaciones en mosAppEcosystem.

Con mosSecurityManager, encripta tráfico y optimiza latencia; mosRTManager añade soporte en tiempo real. En Pro/Enterprise, escala a redes empresariales con balanceo de carga y monitoreo predictivo.

mosNetManager: Conexión sin fronteras. Red inteligente y resiliente.

--- column-end --- 
### mosRTManager

![mosRTManager Icon](_resources/227f705ab4fa3bd9101042c13a656890_MD5.jpg)

**mosRTManager: El Maestro del Tiempo Real en MetsuOS**

mosRTManager es el módulo especializado en operaciones en tiempo real, optimizando latencia y sincronización en entornos dinámicos sobre mosSystemUI. Impulsa multiplayer accesible en mosGameMaker, emulación fluida en mosRetroLauncher y flujos colaborativos en mosDevTool.

Integra con mosNetManager para redes RT y mosTaskManager para priorización crítica. En versiones avanzadas, incorpora predicción IA para jitter y escalabilidad en juegos o automatizaciones.

mosRTManager: Tiempo real impecable. Experiencias instantáneas y accesibles.

--- column-end --- 
### mosSecurityManager


![mosSecurityManager Icon](_resources/00ae6fe49628ac32a524e4e941410c7e_MD5.jpg)

**mosSecurityManager: La Fortaleza Inquebrantable de MetsuOS**

mosSecurityManager es el guardián integral de seguridad que protege datos, procesos y usuarios en todo MetsuOS, sobre mosSystemUI. Implementa encriptación end-to-end, detección de amenazas IA y auditorías continuas, integrándose con mosIAManager para accesos y mosAutomationManager para ejecuciones seguras.

Bloquea vulnerabilidades en apps como mosImageConverter o mosGameMaker, con sandboxing y actualizaciones zero-trust. En Enterprise, añade compliance avanzado y respuesta a incidentes.

mosSecurityManager: Seguridad como prioridad. Privacidad que empodera.

--- column-end --- 
### mosTaskManager

![mosTaskManager Icon](_resources/0ce869892f82d04117656da7b8657ddb_MD5.jpg)

**mosTaskManager: El Director de Orquesta de Tareas en MetsuOS**

mosTaskManager es el gestor de tareas que prioriza, agenda y ejecuta procesos con eficiencia inteligente sobre mosSystemUI. Integra colas dinámicas, dependencias y notificaciones para workflows en mosAutomationManager, builds en mosGameMaker o sincronizaciones en mosGitSync.

Con mosBrainManager, asigna prioridades probabilísticas; mosRTManager maneja tareas críticas. En Pro/Enterprise, soporta equipos con dashboards colaborativos y métricas predictivas.

mosTaskManager: Tareas bajo control. Productividad sin esfuerzo.

 --- column-end ---
--- multi-column-end


## MetsuOS in a Nutshell

### Capas de Infraestructura

```mermaid
graph LR
    A[MetsuOS] --> B[mosLib]
    B --> C[mosSystemCore]
    C --> D[mosSystemUI]
```

### Capa de Servicios

```mermaid
graph LR
    D[mosSystemUI]
    D --> E[mosA11YManager]
    D --> F[mosAutomationManager]
    D --> G[mosBrainManager]
    D --> H[mosIAManager]
    D --> I[mosLegalManager]
    D --> J[mosNetManager]
    D --> K[mosRTManager]
    D --> L[mosSecurityManager]
    D --> M[mosTaskManager]
    E --> N[mosAppEcosystem]
    F --> N[mosAppEcosystem]
    G --> N[mosAppEcosystem]
    H --> N[mosAppEcosystem]
    I --> N[mosAppEcosystem]
    J --> N[mosAppEcosystem]
    K --> N[mosAppEcosystem]
    L --> N[mosAppEcosystem]
    M --> N[mosAppEcosystem]
```


# MetsuOS App Ecosystem: El Ecosistema de Aplicaciones que Impulsa la Creación Inclusiva

```mermaid
graph LR
    A[mosAppEcosystem]
    
    A --> B[mosA11YTools]
    B --> C[mosAutoA11YTester]
    
    A --> D[mosAutomationTools]
    D --> E[mosWorkflowBuilder]
    
    A --> F[mosBrainTools]
    
    A --> G[mosDesignTools]
    G --> H[mosImageConverter]
    G --> I[mosImageEditor]
    
    A --> J[mosDevTools]
    J --> K[mosDiagramGenerator]
    J --> L[mosGitSync]
    
    A --> M[mosGameTools]
    M --> N[mosGameMaker]
    M--> O[mosRetroLauncher]
    
    A --> P[mosIATools]
    P --> Q[mosIAPromptManager]
    
    A --> R[mosLegalTools]
    R --> S[mosComplianceAuditor]
    R --> T[mosContractGenerator]
    R --> U[mosLicenseChecker]
    
    A --> V[mosSecurityTools]
    V --> W[mosPrivacyScanner]
```


> OJO WIP

## mosAppEcosystem

![mosDesignTools](_resources/d119fecc45653ba69bdf21768d76b737_MD5.jpg)  

**Central hub for managing all ecosystem applications.**  

mosAppEcosystem es el núcleo inteligente de MetsuOS: detecta, registra y orquesta automáticamente todos los bloques de herramientas, gestiona sus dependencias, estados y actualizaciones, y los expone de forma unificada y accesible desde mosSystemUI. Actúa como punto único de entrada para lanzar cualquier herramienta en contexto y garantiza que todas respeten las políticas globales de accesibilidad, neutralidad y seguridad.

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```
### mosAutomationTools

![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)  

Herramientas para crear, ejecutar y gestionar flujos de trabajo automatizados, pipelines de construcción y pruebas repetibles dentro del ecosistema MetsuOS.  

Continuar leyendo en mosAutomationTools.md

--- column-end ---
### mosA11YTools

![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)  

Conjunto completo de utilidades y validadores que aseguran la accesibilidad universal en cada proyecto y herramienta del sistema.  

Continuar leyendo en mosA11YTools.md

--- column-end ---
### mosBrainTools

![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)  

Suite dedicada a la validación cognitiva, detección de sesgos y garantía de neutralidad en contenidos generados o importados.  

Continuar leyendo en mosBrainTools.md

--- column-end ---
### mosDesignTools

  ![mosDesignTools](_resources/d119fecc45653ba69bdf21768d76b737_MD5.jpg)

Herramientas de diseño y edición visual accesibles, optimizadas para la creación de assets inclusivos y compatibles con el ecosistema.  

Continuar leyendo en mosDesignTools.md

--- column-end ---
### mosDevTools

![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)  

Entorno extendido de desarrollo con generadores de diagramas, sincronización distribuida y utilidades para programadores dentro de MetsuOS.  

Continuar leyendo en mosDevTools.md

--- column-end ---
### mosGameTools

![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)  

Bloque especializado en la creación, prueba y publicación de videojuegos inclusivos y de código abierto.  

Continuar leyendo en mosGameTools.md

--- column-end ---
### mosIATools

![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)  

Capa de inteligencia artificial ética, local-first y completamente integrada con el resto del ecosistema MetsuOS.  

Continuar leyendo en mosIATools.md

--- column-end ---
### mosLegalTools

![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)  

Utilidades para auditoría de cumplimiento legal, gestión de licencias y generación de documentación normativa.

Continuar leyendo en mosLegalTools.md

--- column-end ---
### mosSecurityTools
![MetsuOS Base Icon](_resources/153129cb093b963dcb3c314f5f80c977_MD5.jpg)  

Escudo de privacidad y seguridad que protege datos, verifica permisos y garantiza la integridad en todo el sistema.

Continuar leyendo en mosSecurityTools.md


 --- column-end ---
--- multi-column-end


![[Plantilla - 1MT#One More Thing]]




