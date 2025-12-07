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
created: 2025-12-05T18:13:49.692Z
modified: 2025-12-06T15:49:47.573Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_011.mp4
---
# Arquitectura Interna de un Gestor de Paquetes Python que Usa Poetry como Backend 🟡③

![Arquitectura Interna de un Gestor de Paquetes Python que Usa Poetry como Backend](PublicBrain/_resources/eed51a6d500a6542fd7fd31b326d7a8d_MD5.jpg)

[[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]
## Introducción

Crear un gestor de paquetes Python desde cero que delegue la mayor parte del trabajo pesado a **Poetry** (específicamente a `poetry-core`) es una estrategia muy potente para aprender cómo funcionan internamente herramientas modernas como Poetry, uv, pipenv o pdm.  

En lugar de reinventar la rueda, nos apoyamos en componentes ya probados y maduros de Poetry, pero los orquestamos con nuestra propia capa de alto nivel. Esta arquitectura nos permite tener un gestor ligero, extensible y perfectamente reproducible, ideal tanto para proyectos educativos como para entornos empresariales con requisitos muy específicos.

Veamos los cinco pilares fundamentales de esta arquitectura: **Core**, **Solver**, **Locker**, **Installer** y **Builder**.

## 1. Core – El director de orquesta

El **Core** es el punto de entrada único del gestor y quien entiende los comandos del usuario (`add`, `install`, `remove`, `lock`, `build`, …).  

Sus tareas principales son:

- Leer y validar el `pyproject.toml`.
- Gestionar la configuración global (ubicación del entorno virtual, caché, repositorios, nivel de paralelismo, etc.).
- Instanciar y coordinar los demás componentes.
- Manejar errores de alto nivel y ofrecer una experiencia de usuario coherente.

```python
class GestorCore:
    def __init__(self, ruta_proyecto: Path = Path.cwd()):
        self.poetry = Factory().create_poetry(ruta_proyecto)  # poetry-core hace el trabajo duro
        self.solver    = ResolverDependencias(self.poetry)
        self.locker    = Bloqueador(self.poetry)
        self.installer = Instalador(self.poetry)
        self.builder   = Constructor(self.poetry)

    def install(self, solo_produccion: bool = False):
        if not self.locker.esta_fresco():
            self.resolver_y_bloquear()
        self.installer.ejecutar(produccion=solo_produccion)
```

Ventaja práctica: el Core puede tener apenas 150-300 líneas y ya ofrece una CLI completa.

## 2. Solver – El cerebro matemático

El **Solver** resuelve el grafo de dependencias. En Poetry se basa en **ResolveLib** + un algoritmo propio de “preferred versions”.  

Funciones clave:

- Construir el “pool” de candidatos desde PyPI y repositorios privados.
- Aplicar marcadores de entorno (`python_version, sys_platform, extra, etc.
- Detectar y reportar conflictos de forma inteligible.
- Reutilizar decisiones previas cuando sea posible (para acelerar `install` sin cambios).

En nuestro gestor podemos usar directamente:

```python
from poetry.puzzle.provider import Provider
from poetry.core.packages.project_package import ProjectPackage

provider = Provider(self.poetry.package, self.poetry.pool, self.poetry.locker)
transaction = provider.solve(self.poetry.package.python_versions)
```

## 3. Locker – La garantía de reproducibilidad

El **Locker** escribe y lee el archivo `poetry.lock` (o un formato propio compatible).  

Responsabilidades:

- Serializar el grafo exacto resuelto (nombre, versión, hash SHA256, fuente).
- Comprobar si el lock está “fresco” comparando metadatos con `pyproject.toml`.
- Permitir actualizaciones parciales (`poetry lock --no-update` estilo).

Poetry ya ofrece una implementación muy robusta que podemos reutilizar casi sin cambios.

## 4. Installer – El operario que ensucia las manos

El **Installer** descarga wheels/sdists y los coloca en el entorno virtual.  

Características importantes que heredamos de Poetry:

- Instalaciones paralelas (`--parallel` o configuración `installer.max-workers`).
- Soporte completo para paquetes editables (`-e`).
- Transacciones atómicas con rollback en caso de error.
- Priorización de wheels precompilados (mucho más rápido que compilar desde sdist).

```python
from poetry.installation.executor import Executor

executor = Executor(env=self.poetry.env, pool=self.poetry.pool, config=self.poetry.config)
executor.execute(operations)  # operations vienen del Locker
```

## 5. Builder – El empaquetador PEP-517/518

El **Builder** genera los artefactos distribuibles (`*.whl` y `*.tar.gz`).  

En Poetry este trabajo lo hace exclusivamente **`poetry-core`**, que implementa el build-backend estándar.  

Solo tenemos que invocar:

```python
from poetry.core.masonry.builders.wheel import WheelBuilder
from poetry.core.masonry.builders.sdist import SdistBuilder

WheelBuilder(self.poetry).build()   # crea dist/mi_paquete-1.0.0-py3-none-any.whl
SdistBuilder(self.poetry).build()   # crea dist/mi_paquete-1.0.0.tar.gz
```

Esto nos da soporte automático para `include`/`exclude`, data-files, entry-points, etc., sin escribir ni una línea de `setup.py`.

## Referencias bibliográficas que **apoyan** esta arquitectura

1. [Repositorio oficial de Poetry (código fuente de todos los componentes descritos) 🟡③🌐](https://github.com/python-poetry/poetry) .- Repositorio oficial de GitHub para Poetry, herramienta de gestión de dependencias y empaquetado en Python que simplifica el uso de pyproject.toml para declaraciones de dependencias, restricciones de versión y grupos opcionales.
2. [Repositorio de poetry-core (el build-backend puro, sin CLI) 🟡③🌐](https://github.com/python-poetry/poetry-core) .- Repositorio oficial de GitHub para poetry-core, implementación ligera del backend de construcción PEP 517 para proyectos gestionados por Poetry, permitiendo builds eficientes sin dependencias completas de Poetry.
3. [Artículo oficial de la PSF – “PEP 517 – A build-system independent format for source trees” 🟡③🌐](https://peps.python.org/pep-0517/) .- Documento oficial PEP 517 que define un formato independiente del sistema de construcción para árboles de origen de paquetes Python, utilizando pyproject.toml para backends y requisitos de build.
4. [Artículo oficial de la PSF – “PEP 518 – Specifying Minimum Build System Requirements” 🟡③🌐](https://peps.python.org/pep-0518/) .- Documento oficial PEP 518 que especifica cómo declarar dependencias del sistema de construcción en pyproject.toml, usando la tabla [build-system] para requisitos como setuptools.
## Referencias que **cuestionan o presentan alternativas** a usar Poetry como backend

1. [Astral – Documentación oficial de uv (el nuevo resolver escrito en Rust, 10-100× más rápido) 🟡③🌐](https://docs.astral.sh/uv/) .- Documentación oficial de uv, gestor de paquetes y proyectos Python extremadamente rápido escrito en Rust, que reemplaza herramientas como pip, Poetry y virtualenv, con características como lockfiles universales, workspaces y benchmarks que muestran 10-100x más rápido que pip.
2. [Ofek Lev – “Hatch project (alternativa completa que no depende de Poetry) 🟡③🌐](https://hatch.pypa.io/latest/) .- Hatch es un gestor de proyectos Python moderno y extensible, independiente de Poetry, con sistema de builds reproducibles, gestión de entornos robusta, soporte para UV, análisis estático con Ruff y CLI responsiva hasta 3x más rápida.


Con estas referencias puedes contrastar objetivamente las ventajas y desventajas de basar tu gestor en Poetry frente a las nuevas generaciones de herramientas (uv, rye, pixi, etc.).  


![[Plantilla - 1MT#One More Thing]]