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
created: 2025-11-29T19:22:44.212Z
modified: 2025-12-03T00:17:20.145Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 12
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_000.mp4
---
# Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③

![Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend](PublicBrain/_resources/d3e9395c77920e9be0ed34f672534abb_MD5.jpg)

* [[MetsuDepManager – Gestor de Dependencias Ético para MetsuOS 🟡③]]

## Módulo 0 – Introducción y motivación

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```
![¿De verdad hace falta otro gestor de paquetes cuando ya existe Poetry? ](PublicBrain/_resources/24d5403e0e4b3f75f98f4d8d933844ac_MD5.jpg)
### 0.1 ¿Realmente es necesario?

En el mundo del desarrollo con Python, donde herramientas como *pip*, *Poetry* o *Conda* han evolucionado hasta convertirse en aliados imprescindibles, es normal que surja esta duda: ¿por qué demonios íbamos a crear un nuevo gestor de dependencias si ya tenemos Poetry, que parece resolverlo todo con elegancia? Poetry, que vio la luz en 2018 y sigue puliéndose en 2025, es una joya: resuelve conflictos de dependencias con astucia, genera entornos reproducibles y se alinea con los estándares modernos como PEP 517 y 518. 

Pero cuando entramos en terrenos específicos como **MetsuOS** —ese sistema operativo modular, adaptable a cualquier plataforma y centrado en la inclusión ética a través de videojuegos, construido sobre la biblioteca *mosLib*—, la cosa cambia. Aquí, la respuesta no es un sí rotundo ni un no tajante, sino un "depende... pero en este caso, sí". Vamos a desgranarlo con calma, reconociendo lo que Poetry hace de maravilla y por qué, para MetsuOS, necesitamos algo como **MetsuDepManager**: un gestor que toma a Poetry como base sólida, pero lo envuelve con capas de control ético y auditoría que van más allá.

Continuar leyendo en ...  [[¿De verdad hace falta otro gestor de paquetes cuando ya existe Poetry?  🟡③]]

--- column-end ---

![Casos reales en los que tiene sentido crear uno propio - empresas con políticas estrictas, entornos educativos, auditorías de seguridad, cumplimiento normativo (RGPD, NIS2, etc.) y air-gapped environments](PublicBrain/_resources/aaf98fa39d495acaf8a5f8c59eeea738_MD5.jpg)
### 0.2. Casos reales en los que tiene sentido crear uno propio: empresas con políticas estrictas, entornos educativos, auditorías de seguridad, cumplimiento normativo (RGPD, NIS2, etc.) y air-gapped environments.

Aunque Poetry es una herramienta excelente y muy madura, en ciertos entornos las organizaciones no pueden necesitar un nivel de control, auditoría y cumplimiento que va más allá de lo que ofrece de forma nativa.

Crear un gestor de paquetes propio basado en Poetry no es una excentricidad técnica, sino una necesidad real en empresas altamente reguladas, instituciones educativas masivas, auditorías estrictas, entornos sujetos a normativas europeas como NIS2 o DORA y, sobre todo, sistemas air-gapped donde cualquier conexión accidental a PyPI está terminantemente prohibida.

Los casos que veremos a continuación no son hipotéticos: son escenarios que ya se dan hoy en bancos del IBEX 35, centrales nucleares, ministerios de defensa y grandes consultoras durante sus

Continuar leyendo en ... [[Casos reales en los que tiene sentido crear uno propio - empresas con políticas estrictas, entornos educativos, auditorías de seguridad, cumplimiento normativo (RGPD, NIS2, etc.) y air-gapped environments 🟡③]]

 --- column-end ---

![Objetivo del Curso - Construir MetsuDepManager, un Gestor de Paquetes Práctico, Ético y Personalizable](PublicBrain/_resources/278da1b50d1680cf6fb27493c9c2e5ba_MD5.jpg)
### 0.3. Objetivo del curso: terminar con un gestor funcional, ético y altamente configurable llamado **MetsuDepManager**

Imagina que estás cansado de que herramientas como pip o Poetry te dejen a merced de dependencias dudosas o entornos que no controlas del todo. Ahí entra este curso de Metsuke: no es solo teoría, sino un camino directo para que termines con **MetsuDepManager** en tus manos, un gestor de paquetes Python que usa Poetry como motor pero añade capas de sentido común y protección real. Al final, tendrás algo que funciona de verdad en proyectos serios, especialmente si trabajas en MetsuOS, ese sistema operativo que apuesta por la inclusión a través de videojuegos. Es como pasar de un coche básico a uno con frenos de emergencia y GPS ético: seguro, adaptable y listo para lo que venga.

Continuar leyendo en ... [[Objetivo del Curso - Construir MetsuDepManager, un Gestor de Paquetes Práctico, Ético y Personalizable 🟡③]]

--- column-end ---

![Requisitos Previos para el Curso de MetsuDepManager - Prepárate sin Complicaciones](PublicBrain/_resources/7ca926b2ca82e9120c0ce1718119fb0c_MD5.jpg)
### 0.4. Requisitos Previos para el Curso de MetsuDepManager - Prepárate sin Complicaciones

Python que pone la ética y la seguridad en el centro, usando Poetry como base—, lo primero es asegurarte de que tu setup no te frene. No te pido que seas un experto, solo que tengas lo básico para no atascarte en los primeros pasos. Piensa en esto como el calentamiento antes de una buena partida: rápido, efectivo y sin sorpresas. Vamos a repasarlo de forma sencilla, con trucos para que lo tengas listo en media hora.

Continua leyendo en ... [[Requisitos Previos para el Curso de MetsuDepManager - Prepárate sin Complicaciones 🟡③]]

--- column-end ---

![MetsuDepManager - Visión general del proyecto](PublicBrain/_resources/bcdb26b402ce1818f324f6b0247f7807_MD5.jpg)
### 0.5. Roadmap del curso y visión general del proyecto final 

El proyecto culminante del curso es MetsuDepManager, un gestor de dependencias para Python diseñado con un enfoque ético y altamente adaptable. 

Funciona como una capa de envoltura segura sobre Poetry, que actúa como su motor principal. Su propósito principal es resolver las carencias de las herramientas actuales en contextos estrictamente regulados, como empresas con normativas internas rigurosas, entornos educativos, auditorías de ciberseguridad o el cumplimiento de regulaciones europeas como el RGPD o la NIS2. 

Además, se adapta perfectamente a sistemas aislados o sin conexión a internet (air-gapped). En su núcleo, prioriza valores como la transparencia total, la auditoría automática, el principio de menor privilegio, la protección de la privacidad y –de forma explícita y no negociable– la accesibilidad universal.

Continuar leyendo en ... [[MetsuDepManager - Visión general del proyecto 🟡③]]

 --- column-end ---
--- multi-column-end<

## Módulo 1 – Entendiendo cómo funciona Poetry por dentro

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```
1.1. Arquitectura interna: Core, Solver, Locker, Installer y Builder  
--- column-end ---
1.2. Diferencias prácticas entre `poetry`, `poetry-core` y los plugins  
--- column-end ---
1.3. Cómo Poetry implementa los estándares PEP 517, 518, 621 y 660  
--- column-end ---
1.4. El `pyproject.toml`: todos los campos (incluso los menos conocidos)  
--- column-end ---
1.5. El `poetry.lock`: estructura TOML y cómo lo genera el solver  
--- column-end ---
1.6. Llamar a Poetry desde código: subprocess vs API pública  
--- column-end ---
1.7. Limitaciones actuales de la API pública (estado en 2025) y soluciones prácticas   
--- column-end ---
--- multi-column-end




### Módulo 2 – Diseño de MetsuDepManager
2.1. Principios básicos: transparencia, ética, auditoría y mínimo privilegio  
2.2. Arquitectura modular: core, CLI, motor de políticas, plugins y UI opcional  
2.3. Elección de herramientas: Typer + Rich, Pydantic v2, structlog  
2.4. Sistema de plugins inspirado en Poetry y pipx  
2.5. ¿Qué significa exactamente “dependencia ética”? (licencias, telemetría, origen, vulnerabilidades)  

### Módulo 3 – Preparación del proyecto
3.1. Estructura definitiva de carpetas  
3.2. `pyproject.toml` propio (sí, usamos Poetry para crear un gestor que envuelve a Poetry)  
3.3. Herramientas de calidad: pre-commit, ruff, mypy, pytest, coverage  
3.4. CI completo con GitHub Actions (tests, lint, release y publicación)  
3.5. Primer comando funcional: `metsudep --version`  

### Módulo 4 – Wrapper seguro sobre Poetry
4.1. Clase `PoetryBackend` y ejecución controlada  
4.2. Uso seguro de la API interna de Poetry (`poetry.console.application`)  
4.3. Filtrado de salida (ocultar tokens, rutas sensibles)  
4.4. Timeouts y límites de recursos  
4.5. Modo dry-run global  
4.6. Logging estructurado con structlog  

### Módulo 5 – Motor de políticas éticas (Policy Engine)
5.1. Archivo de configuración `metsudep.toml` / `metsudep.yaml`  
5.2. Políticas por defecto:  
 • Licencias permitidas y prohibidas (SPDX)  
 • Bloqueo de paquetes con telemetría conocida  
 • Repositorios permitidos  
 • Umbral de vulnerabilidades  
 • Versiones mínimas de seguridad  
5.3. Integración con Safety, OSS Index, OSV y PyPI advisories  
5.4. Excepciones firmadas criptográficamente  
5.5. Generación automática de SBOM (CycloneDX y SPDX)  

### Módulo 6 – Interfaz de línea de comandos (CLI)
6.1. Comandos principales: `init`, `add`, `remove`, `update`, `install`, `lock`, `build`, `publish`  
6.2. Comandos avanzados: `audit`, `policy`, `sign-exception`, `verify-sbom`  
6.3. Tablas bonitas y árboles de dependencias con Rich  
6.4. Barras de progreso y spinners en tiempo real  
6.5. Autocompletado en bash/zsh/fish  

### Módulo 7 – Entornos aislados y modo sandbox
7.1. Creación de entornos 100 % herméticos  
7.2. Compatibilidad opcional con virtualenv, venv, conda y pixi  
7.3. Pinning absoluto con hash + URL directa  
7.4. Funcionamiento 100 % offline con cache local obligatorio  

### Módulo 8 – Sistema de plugins
8.1. Entry-points oficiales `metsudep.plugin`  
8.2. Hooks: `pre_add`, `post_install`, etc.  
8.3. Ejemplos reales de plugins incluidos en el curso  

### Módulo 9 – Integración en CI/CD y empresas
9.1. Exportación a `requirements.txt` y `conda-environment.yml`  
9.2. GitHub Actions reutilizables para validar políticas en Pull Requests  
9.3. Modo “enforcer” que bloquea merges si fallan las políticas  

### Módulo 10 – Testing serio
10.1. Tests unitarios e integración con pytest-subprocess  
10.2. Property-based testing con Hypothesis  
10.3. Cobertura obligatoria > 95 %  

### Módulo 11 – Publicación y distribución
11.1. Construcción y publicación automática en PyPI  
11.2. Opcional: binarios standalone con PyInstaller o Nuitka  

### Módulo 12 – Proyecto final y ideas futuras
12.1. Checklist de “production-ready”  
12.2. Extensiones posibles: UI web, soporte multi-lenguaje, integración con gestores del sistema operativo  
12.3. Cómo contribuir al proyecto open-source  
### Anexos
- Comandos rápidos  
- Plantilla completa de `metsudep.toml`  
- Licencias permitidas por defecto  
- Glosario y recursos adicionales  

## Referencias bibliográficas que apoyan el contenido

1. [Documentación oficial de Poetry (2025) – Arquitectura y API pública 🟡③🌐](https://python-poetry.org/docs/) .- Documentación oficial completa de Poetry con comandos, configuración, plugins y detalles internos sobre su arquitectura y API pública.
2. [PEP 517 – A build-system independent packaging format 🟡③🌐](https://peps.python.org/pep-0517/) .- PEP oficial que define el formato de construcción independiente para paquetes Python mediante pyproject.toml y hooks de backend.
3. [PEP 518 – Specifying Minimum Build System Requirements 🟡③🌐](https://peps.python.org/pep-0518/) .- PEP oficial que establece cómo especificar requisitos mínimos del sistema de construcción en proyectos Python usando pyproject.toml.
4. [PEP 621 – Storing project metadata in pyproject.toml 🟡③🌐](https://peps.python.org/pep-0621/) .- PEP oficial que detalla el almacenamiento de metadatos centrales del proyecto en el archivo pyproject.toml para herramientas de empaquetado.
5. [Safety (pyup.io) – Documentación oficial y base de datos de vulnerabilidades 🟡③🌐](https://github.com/pyupio/safety) .- Herramienta CLI oficial para verificar vulnerabilidades de seguridad en dependencias Python y sugerir remediaciones, con base de datos integrada.
6. [OSV – Open Source Vulnerabilities database (Google) 🟡③🌐](https://osv.dev/) .- Base de datos distribuida de vulnerabilidades para software de código abierto, mantenida por Google con soporte para múltiples ecosistemas.
7. [CycloneDX – Especificación oficial de SBOM 🟡③🌐](https://cyclonedx.org/) .- Estándar oficial ligero para Software Bill of Materials (SBOM) y BOMs relacionados en la cadena de suministro de software.
8. [SPDX – Licencias y formato SBOM 🟡③🌐](https://spdx.dev/) .- Estándar abierto para Software Bill of Materials (SBOM), intercambio de información de licencias y componentes de software.
9. [Typer – Documentación oficial (creado por el autor de FastAPI) 🟡③🌐](https://typer.tiangolo.com/) .- Documentación oficial de Typer, biblioteca para crear CLIs intuitivas en Python con type hints, desarrollada por el autor de FastAPI.
10. [Rich – Biblioteca de renderizado en terminal 🟡③🌐](https://github.com/Textualize/rich) .- Biblioteca Python para texto enriquecido, formateo hermoso y elementos visuales en terminales.

## Referencias que cuestionan o matizan la necesidad de crear otro gestor

1. [Paul Moore (maintainer de pip) – Discusión sobre la fragmentación del ecosistema Python (2023) 🟡③🌐](https://discuss.python.org/t/python-packaging-strategy-discussion-part-1/22420) .- Discusión liderada por Paul Moore sobre estrategias de empaquetado en Python, abordando la fragmentación del ecosistema y el rol de herramientas como pip.

Estas referencias críticas no invalidan el curso (los casos de uso empresariales y educativos siguen siendo válidos), pero sí invitan a reflexionar sobre si en muchos casos basta con configurar bien Poetry + plugins existentes antes de crear una herramienta nueva.

![[Plantilla - 1MT#One More Thing]]