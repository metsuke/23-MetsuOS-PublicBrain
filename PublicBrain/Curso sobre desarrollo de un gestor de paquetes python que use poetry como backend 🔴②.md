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
modified: 2025-11-29T21:15:38.009Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_000.mp4
---
# Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🔴②

![Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend](PublicBrain/_resources/d3e9395c77920e9be0ed34f672534abb_MD5.jpg)

* [[MetsuDepManager – Gestor de Dependencias Ético para MetsuOS 🟡③]]

> OJO WIP
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

Continuar leyendo en ...  [[¿De verdad hace falta otro gestor de paquetes cuando ya existe Poetry? 🔴②]]

 --- column-end ---

0.2. Casos reales en los que tiene sentido crear uno propio: empresas con políticas estrictas, entornos educativos, auditorías de seguridad, cumplimiento normativo (RGPD, NIS2, etc.) y air-gapped environments  
0.3. Objetivo del curso: terminar con un gestor funcional, ético y altamente configurable llamado **MetsuDepManager**  
0.4. Requisitos previos: Python ≥ 3.9, conocimientos básicos de Poetry, Git y línea de comandos  
0.5. Roadmap del curso y visión general del proyecto final  

 --- column-end ---
--- multi-column-end

### Módulo 1 – Entendiendo cómo funciona Poetry por dentro
1.1. Arquitectura interna: Core, Solver, Locker, Installer y Builder  
1.2. Diferencias prácticas entre `poetry`, `poetry-core` y los plugins  
1.3. Cómo Poetry implementa los estándares PEP 517, 518, 621 y 660  
1.4. El `pyproject.toml`: todos los campos (incluso los menos conocidos)  
1.5. El `poetry.lock`: estructura TOML y cómo lo genera el solver  
1.6. Llamar a Poetry desde código: subprocess vs API pública  
1.7. Limitaciones actuales de la API pública (estado en 2025) y soluciones prácticas  

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

> OJO WIP

1. Documentación oficial de Poetry (2025) – Arquitectura y API pública  
   https://python-poetry.org/docs/

2. PEP 517 – A build-system independent packaging format  
   https://peps.python.org/pep-0517/

3. PEP 518 – Specifying Minimum Build System Requirements  
   https://peps.python.org/pep-0518/

4. PEP 621 – Storing project metadata in pyproject.toml  
   https://peps.python.org/pep-0621/

5. Safety (pyup.io) – Documentación oficial y base de datos de vulnerabilidades  
   https://github.com/pyupio/safety

6. OSV – Open Source Vulnerabilities database (Google)  
   https://osv.dev/

7. CycloneDX – Especificación oficial de SBOM  
   https://cyclonedx.org/

8. SPDX – Licencias y formato SBOM  
   https://spdx.dev/

9. Typer – Documentación oficial (creado por el autor de FastAPI)  
   https://typer.tiangolo.com/

10. Rich – Biblioteca de renderizado en terminal  
    https://github.com/Textualize/rich

## Referencias que cuestionan o matizan la necesidad de crear otro gestor

> OJO WIP

1. Brett Cannon (2021) – “Why you probably don’t need to write your own package manager” (PyCon US 2021)  
   https://www.youtube.com/watch?v=3v6KqDD5JYo

2. Paul Moore (maintainer de pip) – Discusión sobre la fragmentación del ecosistema Python (2023)  
   https://discuss.python.org/t/should-we-consider-deprecating-requirements-txt/27945

3. Dustin Ingram (PyPI & Google) – “The State of Python Packaging 2024” (PyCon US 2024)  
   https://www.youtube.com/watch?v=5nX9wX3_q9U

4. Artículo “The Python packaging iceberg” – Henry Schreiner (2024)  
   https://henryschreiner.dev/blog/2024/python-packaging-iceberg/

5. “Poetry 2.0 Roadmap” – Anuncio oficial (2024-2025) que incluye muchas mejoras de auditoría y políticas  
   https://github.com/python-poetry/poetry/issues/7088

Estas referencias críticas no invalidan el curso (los casos de uso empresariales y educativos siguen siendo válidos), pero sí invitan a reflexionar sobre si en muchos casos basta con configurar bien Poetry + plugins existentes antes de crear una herramienta nueva.

![[Plantilla - 1MT#One More Thing]]