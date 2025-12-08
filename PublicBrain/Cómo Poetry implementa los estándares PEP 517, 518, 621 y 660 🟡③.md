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
created: 2025-12-07T13:01:27.425Z
modified: 2025-12-08T17:59:30.604Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 7
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_013.mp4
---
# Cómo Poetry implementa los estándares PEP 517, 518, 621 y 660 🟡③

![Cómo Poetry implementa los estándares PEP 517, 518, 621 y 660 ](PublicBrain/_resources/a1f5caf5bb1565420ee2485afb340d89_MD5.jpg)

[[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

Poetry no solo actúa como gestor de dependencias, sino también como backend de construcción que se alinea con los estándares modernos del ecosistema Python. Estos estándares, definidos en las PEPs (Python Enhancement Proposals) 517, 518, 621 y 660, permiten builds reproducibles, configuraciones declarativas y flujos de desarrollo más fluidos. 

En esta lección, desglosamos de manera clara y práctica cómo Poetry los pone en marcha, con ejemplos reales que puedes probar en tu propio proyecto. El enfoque del curso, resalta cómo estos PEPs convierten a Poetry en un aliado ideal para extensiones como MetsuDepManager, donde la auditoría y la reproducibilidad son clave.

## PEP 517: Un Formato de Empaquetado Independiente del Sistema de Construcción

El PEP 517 marca un antes y un después al separar el "frontend" (como pip) del "backend" de construcción, eliminando la dependencia de archivos como `setup.py`. Poetry lo implementa a través de **poetry-core**, un módulo ligero que sirve como backend conforme a este estándar. Esto significa que puedes construir tu proyecto con herramientas externas sin instalar Poetry al completo; basta con `poetry-core` para generar distribuciones fuente (sdist) o wheels.

En la práctica, Poetry configura la tabla `[build-system]` en `pyproject.toml` para invocar hooks como `build_wheel` o `get_requires_for_build_sdist`. Esto acelera los builds en entornos de CI/CD y asegura independencia. Por ejemplo, en el curso, al invocar estos hooks vía subprocess o la API de Poetry (Lección 1.6), se logra una integración perfecta para MetsuDepManager, resolviendo problemas de reproducibilidad en setups aislados.

Aquí un ejemplo básico de `pyproject.toml` generado con `poetry init`:

```toml
[build-system]
requires = ["poetry-core>=1.0.0"]
build-backend = "poetry.core.masonry.api"
```

Con esto, un simple `pip install .` construye el paquete sin más complicaciones.

## PEP 518: Especificación de Requisitos Mínimos del Sistema de Construcción

Este PEP resuelve el clásico "catch-22" de los builds: ¿cómo instalar dependencias de construcción si el build las necesita? Poetry lo maneja de forma nativa en `[build-system]`, instalando automáticamente las dependencias listadas en `requires` en un entorno aislado antes de proceder.

Al ejecutar `poetry install` o un build, Poetry resuelve e instala temporalmente paquetes como `setuptools` o `wheel`, garantizando consistencia incluso con extensiones en C. En el contexto del curso (Módulo 3.2), esto es esencial para configurar MetsuDepManager sin conflictos globales, permitiendo envolver Poetry sin reinstalar nada innecesario.

Ejemplo extendido:

```toml
[build-system]
requires = ["poetry-core>=1.0.0", "setuptools>=45"]
build-backend = "poetry.core.masonry.api"
```

Poetry valida esta sección al vuelo, usando su resolvedor para detectar incompatibilidades tempranamente.

## PEP 621: Almacenamiento de Metadatos del Proyecto en pyproject.toml

El PEP 621 estandariza cómo guardar metadatos como nombre, versión o autores en `pyproject.toml`, fomentando una configuración única y compatible. Poetry lo soporta desde la versión 1.2 y, en su madura 2.0 (lanzada en 2025), migra completamente a la tabla `[project]`, aunque mantiene `[tool.poetry]` para funciones específicas como grupos de dependencias.

Esto permite declarar dependencias runtime en `[project.dependencies]` y exportar a `requirements.txt` con `poetry export`. En el curso (Lecciones 1.3 y 1.4), se usa para reemplazar `setup.py` en MetsuDepManager, mejorando la interoperabilidad con pip y Twine.

Ejemplo para un proyecto ético:

```toml
[project]
name = "metsudepmanager"
version = "0.1.0"
description = "Gestor ético de dependencias usando Poetry"
authors = [{name = "Raul Carrillo aka Metsuke", email = "metsuke@gmail.com"}]
dependencies = [
    "poetry-core>=1.0.0",
    "typer>=0.9.0",
    "rich>=13.0.0"
]
readme = "README.md"
requires-python = ">=3.11"
license = "GPL-3.0-or-later"
classifiers = [
	"License :: OSI Approved :: GNU General Public License v3 or later (GPLv3+)"
]
```

La licencia es GPL v3 según lo argumentado en [[PublicBrain/¿Qué licencia debe tener MetsuDepManager? 🟡③]], decisión tomada a 8 de Diciembre de 2025.

Para extras, recurre a `[dependency-groups]` (PEP 735) o grupos de Poetry.

## PEP 660: Instalaciones Editables (Modo de Desarrollo)

Este PEP extiende los anteriores para instalaciones editables, enlazando el código fuente directamente sin copias, ideal para iterar durante el desarrollo. Poetry lo habilita por defecto con `poetry install`, que enlaza el proyecto actual en modo editable vía `poetry-core`.

Soporta `pip install -e .` desde la 1.2, usando symlinks o paths directos para cambios en vivo. En el curso (Módulo 1.3 y workflows de desarrollo), esto acelera la iteración en MetsuDepManager sin rebuilds constantes, integrándose con `poetry.lock` para audits en installs editables.

Ejemplo de comando:

```bash
poetry install  # Instala dependencias + proyecto en editable (PEP 660)
# O con pip:
pip install -e .  # Backend de poetry-core maneja lo editable
```

## Integración en el Curso y Beneficios Prácticos

El curso de MetsuKe posiciona estos PEPs como el núcleo de MetsuDepManager: un wrapper que invoca Poetry vía API o subprocess (Lección 1.6) para builds auditables y éticos. Los beneficios son claros: builds rápidos y reproducibles, compatibilidad total con pip/Twine y menos fricciones en el packaging. En 2025, con Poetry 2.0, `pyproject.toml` se consolida como la fuente única de verdad, alineándose con el ecosistema Python. Si estás desarrollando paquetes, empieza con `poetry init` y explora estos estándares; verás cómo simplifican todo.

# Referencias Bibliográficas de Apoyo

1. [PEP 517 – A build-system independent format for source trees 🟡③🌐](https://peps.python.org/pep-0517/) .- Propuesta oficial que define el formato independiente para frontends y backends de construcción, implementado por Poetry vía poetry-core para builds reproducibles.
2. [PEP 518 – Specifying Minimum Build Dependencies in pyproject.toml 🟡③🌐](https://peps.python.org/pep-0518/) .- Documento que estandariza la declaración de dependencias de build en pyproject.toml, adoptado por Poetry para entornos aislados.
3. [PEP 621 – Storing project metadata in pyproject.toml 🟡③🌐](https://peps.python.org/pep-0621/) .- Especificación para metadatos en pyproject.toml, soportada por Poetry desde v1.2 y fully integrada en v2.0 para configuraciones declarativas.
4. [PEP 660 – Editable installs for pyproject.toml based builds 🟡③🌐](https://peps.python.org/pep-0660/) .- Extensión para instalaciones editables, habilitada en Poetry con poetry install para desarrollo ágil.
5. [Documentación oficial de Poetry: pyproject.toml 🟡③🌐](https://python-poetry.org/docs/pyproject/) .- Guía detallada sobre la implementación de PEPs en Poetry, con ejemplos de [build-system] y [project].
6. [The Basics of Python Packaging in Early 2023 (actualizado 2025) 🟡③🌐](https://drivendata.co/blog/python-packaging-2023) .- Análisis práctico de PEPs 517, 518 y 621 en herramientas como Poetry, con énfasis en backends modernos.
7. [[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]] .- Roadmap del curso de MetsuKe, con Módulo 1.3 dedicado a la implementación de estos PEPs en wrappers como MetsuDepManager.

# Referencias Bibliográficas Críticas o de Refutación

1. [Pain points of moving to Poetry? (Discusión en Reddit) 🟡③🌐](https://www.reddit.com/r/Python/comments/y3vzho/pain_points_of_moving_to_poetry/) .- Hilo comunitario que critica la no conformidad inicial de Poetry con PEP 621, destacando problemas de compatibilidad legacy hasta v2.0.
2. [Python Package Manager Comparison (DEV Community) 🟡③🌐](https://dev.to/adamghill/python-package-manager-comparison-1g98) .- Comparativa que señala como limitación la parcial adherencia de Poetry a PEPs, comparado con herramientas más estrictas como Hatch.
3. [What's the difference between the tool.poetry and project tables in pyproject.toml? (Stack Overflow) 🟡③🌐](https://stackoverflow.com/questions/75408641/whats-the-difference-between-the-tool-poetry-and-project-tables-in-pyprojec) .- Debate sobre la dualidad de secciones en Poetry, criticando su migración lenta a PEP 621 y el uso de formatos custom.
4. [Navigating the Python Packaging Landscape: Pip vs. Poetry vs. uv (Medium) 🟡③🌐](https://dimasyotama.medium.com/navigating-the-python-packaging-landscape-pip-vs-poetry-vs-uv-a-developers-guide-49a9c93caf9c) .- Artículo que refuta la superioridad absoluta de Poetry en PEPs, apuntando a lentitud en resolución de dependencias y adopción incompleta hasta 2025.
5. [Vídeo: Is Python making Poetry REDUNDANT?! (YouTube, Very Academy) 🟡③🌐](https://www.youtube.com/watch?v=xjDXLRXl8WI) .- Análisis que cuestiona la relevancia de Poetry ante PEPs como 735, destacando limitaciones en editable installs y grupos de dependencias pre-v2.0.
6. [`poetry add`, but for PEP 621? (Discusiones Python.org) 🟡③🌐](https://discuss.python.org/t/poetry-add-but-for-pep-621/22957) .- Conversación que critica la falta de comandos nativos para editar secciones PEP 621 en Poetry, proponiendo herramientas externas como solución temporal.


![[Plantilla - 1MT#One More Thing]]