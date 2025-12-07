---
iaStatus_Model: Grok-4, Raul Carrillo aka Metsuke
iaStatus: 8
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-12-06T16:17:34.700Z
modified: 2025-12-07T00:25:16.804Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_012.mp4
---
# Elegimos exactamente qué partes de Poetry vamos a usar en MetsuDepManager 🟡③

![Elegimos exactamente qué partes de Poetry vamos a usar en MetsuDepManager](PublicBrain/_resources/ae6b1671a69e89a877bcf5f09fbc63d4_MD5.jpg)

[[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

En este punto ya sabemos que no vamos a reinventar la rueda. Vamos a reutilizar lo mejor de Poetry, pero con control total: sin telemetría, con timeouts, con auditoría y funcionando en entornos air-gapped.

La decisión práctica que tomamos hoy (y que vamos a codificar ya mismo) es esta:

| Necesidad                                 | Fuente elegida                          | Motivo real (2025)                                          |
|-------------------------------------------|-----------------------------------------|-------------------------------------------------------------|
| Resolver dependencias y generar lock      | `poetry-core` (API pura)                | Control total, timeout, objetos Python, sin stdout          |
| Instalar paquetes en el venv              | `poetry-core` → `Installer.run()`       | Podemos inspeccionar cada paquete antes de instalarlo      |
| Construir wheel/sdist                     | `poetry-core` → `Builder`               | Inyectamos metadatos éticos y SBOM                          |
| Comandos rápidos que el usuario conoce   | binario `poetry` vía subprocess         | Estables y el usuario ya los sabe usar                      |
| Bloqueo de telemetría y auditoría automática | plugin propio (`metsudep-plugin-ethics`)| Se ejecuta solo, sin intervención del usuario               |

Hoy vamos a hacer tres cosas concretas (y las vamos a dejar funcionando):

## 1. El primer wrapper híbrido real (70 % poetry-core + 30 % subprocess)

Archivo: `metsudep/core/backend.py`

```python
from __future__ import annotations
import subprocess
from pathlib import Path
from poetry.core.factory import Factory
from poetry.core.installation.installer import Installer
from poetry.core.execution.executor import Executor
from poetry.core.utils.env import VirtualEnv

class PoetryBackend:
    def __init__(self, cwd: Path | None = None):
        self.cwd = Path(cwd or Path.cwd())
        self.poetry = Factory().create_poetry(self.cwd)  # API pública y estable

    # 1. Operaciones rápidas → subprocess (más simple y estable)
    def lock_check(self) -> bool:
        result = subprocess.run(
            ["poetry", "lock", "--check"],
            cwd=self.cwd,
            capture_output=True,
            text=True,
            timeout=60,
        )
        return result.returncode == 0

    def export_requirements(self, output: Path, format: str = "requirements.txt") -> None:
        subprocess.run(
            ["poetry", "export", "-f", format, "-o", str(output), "--without-hashes"],
            check=True,
            cwd=self.cwd,
            timeout=120,
        )

    # 2. Operaciones críticas → poetry-core puro (control total)
    def install_with_audit(self, dry_run: bool = False) -> int:
        env = VirtualEnv(self.poetry.file.path.parent / ".venv")
        installer = Installer(
            io=self.poetry.io,          # puedes usar un IO custom para logs
            env=env,
            package=self.poetry.package,
            locker=self.poetry.locker,
            pool=self.poetry.pool,
            config=self.poetry.config,
            executor=Executor(env, self.poetry.pool, self.poetry.config),
        )
        installer.whitelist(["requests", "numpy"])  # ejemplo de política
        installer.verbose(True)
        return installer.run(dry_run=dry_run, timeout=300)
```

## 2. Clases públicas y estables de poetry-core en 2025

Estas son las que puedes importar sin miedo a que rompan en versiones menores (confirmado en el CHANGELOG oficial 2.2.0+):

| Clase/Objeto                     | Ruta de importación                              | Uso recomendado en MetsuDepManager       |
|----------------------------------|--------------------------------------------------|------------------------------------------|
| `Factory().create_poetry()`      | `poetry.core.factory.Factory`                    | Lectura de pyproject.toml y lock         |
| `Installer`                      | `poetry.core.installation.installer.Installer`   | Instalación con control total            |
| `Solver`                         | `poetry.core.packages.dependency_solver.Solver`  | Resolución personalizada                 |
| `Builder`                        | `poetry.core.masonry.api`                        | Build con SBOM y metadatos extra         |
| `Locker`                         | `poetry.core.poetry.Locker`                      | Escritura/lectura segura del lock        |

## 3. La frontera definitiva que vas a usar desde hoy


Regla de oro (pégala en tu README interno):

```text
┌─────────────────────────────────────────────────────────────────────────────────┐
│  ¿Necesitas timeout, cancelación o inspeccionar paquetes? → poetry-core         │
│  ¿Es un comando que el usuario final ya conoce y es idempotente? → subprocess   │
│  ¿Quieres que se ejecute siempre sin acordarte? → plugin                        │
└─────────────────────────────────────────────────────────────────────────────────┘
```

Con esto ya tienes el esqueleto funcional del backend híbrido que vas a ir enriqueciendo en los próximos módulos.

## Referencias que apoyan este enfoque

1. [poetry-core API pública y estable 🟡③🌐](https://pypi.org/project/poetry-core/) .- Implementación ligera y estable del backend de construcción PEP 517 para Poetry, versión 2.2.1 lanzada el 21 de septiembre de 2025, compatible con Python >=3.9.
2. [Real Python – Dependency Management with Poetry (2024, actualizado 2025) 🟡③🌐](https://realpython.com/dependency-management-python-poetry/) .- Tutorial sobre gestión de dependencias con Poetry, cubriendo instalación, creación de proyectos, declaración de dependencias y entornos virtuales, actualizado en 2025.

## Referencias que critican Poetry (para que tengas contraargumentos)

1. [“Why I stopped using Poetry” – ArjanCodes (2024) 🟡③🌐](https://www.youtube.com/watch?v=Gr9o8MW_pb0) .- Video explaining reasons for abandoning Poetry, including dependency conflicts, redundancy with pip and pip-tools, and loss of trust due to maintainer decisions on script deprecation.
2. [Comparativa 2025 uv vs Poetry – Medium (diciembre 2025) 🟡③🌐](https://medium.com/@asma.shaikh_19478/python-packaging-in-2025-uv-vs-poetry-vs-pip-tools-8dfcb98aa54e) .- Article comparing uv, Poetry, and pip-tools for Python dependency management in 2025, emphasizing tool selection based on workflow needs.


![[Plantilla - 1MT#One More Thing]]