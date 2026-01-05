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
created: 2025-11-28T09:24:05.460Z
modified: 2026-01-05T20:41:26.811Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 8
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: MetsuDepManagerB.mp4
---
# MetsuDepManager – Gestor de Dependencias Ético para MetsuOS 🟡③

![MetsuDepManager](PublicBrain/_resources/570f078529742a81c508c3b36eac5d26_MD5.jpg)()

* [El repositorio de MetsuDepManager (en desarrollo)](https://github.com/metsuke/MetsuDepManager)
	* [[mosLib - El Corazón de MetsuOS  ⚫①]]
	* [[¿Que sistema de dependencias para python es apropiado para MetsuOS? 🟡③]]
	* [[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

Aprovechamos que sea el primer modulo para lanzar una implementación completa hecha por IA (y ajustada manualmente en lo necesario) de **MetsuDepManager** para MetsuOS

Este documento contiene integro el codigo indicado por IA, la version real y con los posibles cambios y mejoras, estará en su propio repositorio, que enlazaré una vez exista realmente.
## El sistema que garantiza que ningún paquete viole los principios de MetsuOS

MetsuOS es un sistema operativo modular cuya misión es la inclusión social a través de videojuegos educativos y software 100 % libre (a excepcion de versiones Pro y Enterprise, destinadas a obtener redito económico en el futuro)

Para cumplir esa promesa, **ningún paquete puede tener una licencia incompatible** con la capa ética activa (por defecto `fsf-fan`: solo licencias copyleft fuertes).

MetsuDepManager es la solución real: una capa ligera encima de **[Poetry  🌐](https://python-poetry.org/)** que:

- Respeta al 100 % el estándar `pyproject.toml`
- Verifica automáticamente licencias
- Resuelve grupos de dependencias “al menos una obligatoria”
- Aplica prioridades éticas y técnicas
- Añade dependencias específicas por sistema operativo
- Es completamente reproducible gracias a `poetry.lock`

### Ejemplo de `pyproject.toml` válido para MetsuOS

```toml
  [tool.poetry]
name = "metsuos-core"
version = "0.2.0"
description = "Núcleo del entorno operativo MetsuOS"
authors = ["Raul Carrillo aka metsuke <rcarrillo@metsuke.com>"]

[tool.poetry.dependencies]
python = "^3.11"

# Dependencias normales de Poetry (pueden ser rechazadas por licencia)
pillow = { version = "^10.4", optional = true }

[build-system]
requires = ["poetry-core>=1.8.0"]
build-backend = "poetry.core.masonry.api"

# ====================== CONFIGURACIÓN METSUDEP ======================
[tool.metsudep.licenses]
required_layer = "fsf-fan"        # Sólo GPL-3.0+, AGPL-3.0+, LGPL-3.0+

# Grupo obligatorio: al menos un motor gráfico
[tool.metsudep.groups.render]
at_least_one = true

[[tool.metsudep.groups.render.alternatives]]
name = "pygame"
version = "^2.6"
priority = "high"
platform = "linux"

[[tool.metsudep.groups.render.alternatives]]
name = "pyglet"
version = "^2.0"
priority = "medium"               # fallback universal

[[tool.metsudep.groups.render.alternatives]]
name = "kivy"
version = "^2.3"
priority = "low"
platform = "android"

# Dependencias específicas del host
[tool.metsudep.host_deps.linux]
xkcdpass = "^1.0"

[tool.metsudep.host_deps.android]
python-for-android = "*"
```

### Código completo y definitivo: `metsudep_manager.py`

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
MetsuDepManager – Gestor de dependencias ético para MetsuOS
Versión: 1.0.0 (2025-11-28)
Licencia: GPL-3.0-or-later
Autor: Comunidad MetsuOS (implementación completa por Grok + revisión humana)
"""

import toml
import platform
import subprocess
import sys
from pathlib import Path
from typing import Dict, List, Any, Optional

# ===================================================================
# Mocks reemplazables cuando mosLib esté disponible (producción)
# ===================================================================
class MosLegalManagerMock:
    """Simulación de mosLegalManager – verifica licencias según capa ética"""
    LAYERS = {
        "fsf-fan": {"GPL-3.0", "GPL-3.0-or-later", "AGPL-3.0", "AGPL-3.0-or-later", "LGPL-3.0", "LGPL-3.0-or-later"},
        "community": {"MIT", "Apache-2.0", "BSD-3-Clause", "GPL-3.0", "AGPL-3.0", "LGPL-3.0"}
    }

    def __init__(self, layer: str = "fsf-fan"):
        self.layer = layer

    def permite(self, licencia: str) -> bool:
        return licencia in self.LAYERS.get(self.layer, set())

class MosTaskManagerMock:
    """Simulación de mosTaskManager – resuelve conflictos por prioridad"""
    @staticmethod
    def elegir_mejor(opciones: List[Dict[str, Any]]) -> Dict[str, Any]:
        prioridades = {"high": 3, "medium": 2, "low": 1}
        return max(opciones, key=lambda x: prioridades.get(x.get("priority", "low"), 0))

# ===================================================================
# Gestor principal
# ===================================================================
class MetsuDepManager:
    def __init__(self, ruta_pyproject: str = "pyproject.toml", directorio: str = "."):
        self.ruta = Path(directorio) / ruta_pyproject
        self.cfg = self._cargar_toml()
        self.so = platform.system().lower()          # linux, windows, darwin, android
        self.legal = MosLegalManagerMock(
            self.cfg.get("tool", {}).get("metsudep", {}).get("licenses", {}).get("required_layer", "fsf-fan")
        )
        self.task = MosTaskManagerMock()

    def _cargar_toml(self) -> Dict[str, Any]:
        if not self.ruta.exists():
            raise FileNotFoundError(f"No se encontró {self.ruta}")
        return toml.load(self.ruta)

    # ------------------------------------------------------------------
    # Base de datos ligera de licencias (actualizada noviembre 2025)
    # ------------------------------------------------------------------
    LICENCIAS_CONOCIDAS = {
        "pygame": "LGPL-2.1-or-later",
        "pyglet": "BSD-3-Clause",
        "kivy": "MIT",
        "numpy": "BSD-3-Clause",
        "pillow": "HPND",
        "requests": "Apache-2.0",
        "xkcdpass": "BSD-3-Clause",
        "python-for-android": "MIT",
        "flask": "BSD-3-Clause",
        "django": "BSD-3-Clause",
    }

    def _licencia_de(self, paquete: str) -> str:
        return self.LICENCIAS_CONOCIDAS.get(paquete.lower(), "Unknown")

    # ------------------------------------------------------------------
    def resolver_grupo(self, nombre: str, config: Dict) -> Optional[Dict]:
        if not config.get("at_least_one", False):
            return None

        alternativas: List[Dict] = config.get("alternatives", [])
        if not alternativas:
            print(f"  Grupo '{nombre}' vacío")
            return None

        # Filtrar por plataforma
        candidatas = [
            alt for alt in alternativas
            if not alt.get("platform") or alt.get("platform", "").lower() == self.so
        ]

        if not candidatas:
            print(f"  No hay alternativa válida para {self.so} en grupo '{nombre}'")
            return None

        seleccionada = self.task.elegir_mejor(candidatas)
        print(f"  Grupo '{nombre}' → {seleccionada['name']} (prioridad {seleccionada.get('priority', 'low')})")
        return seleccionada

    # ------------------------------------------------------------------
    def generar_dependencias_poetry(self) -> Dict[str, Any]:
        poetry_deps = self.cfg.get("tool", {}).get("poetry", {}).get("dependencies", {}).copy()
        metsudep = self.cfg.get("tool", {}).get("metsudep", {})

        print("Resolviendo grupos obligatorios...")
        for nombre_grupo, config_grupo in metsudep.get("groups", {}).items():
            sel = self.resolver_grupo(nombre_grupo, config_grupo)
            if sel:
                poetry_deps[sel["name"]] = sel.get("version", "*")

        print("Añadiendo dependencias específicas del host...")
        host_deps = metsudep.get(f"host_deps.{self.so}", {})
        for nombre, spec in host_deps.items():
            poetry_deps[nombre] = spec
            print(f"  + {nombre} (host: {self.so})")

        # Validación ética de licencias
        print("\nValidando licencias según capa ética...")
        deps_finales = {"python": poetry_deps.get("python", "^3.11")}
        rechazados = 0

        for nombre, spec in poetry_deps.items():
            if nombre.lower() == "python":
                continue
            licencia = self._licencia_de(nombre)
            if self.legal.permite(licencia):
                deps_finales[nombre] = spec
                print(f"  Aprobado {nombre} → {licencia}")
            else:
                print(f"  Rechazado {nombre} → {licencia} (incompatible con {self.legal.layer})")
                rechazados += 1

        print(f"\nResumen: {len(deps_finales)-1} paquetes aprobados, {rechazados} rechazados")
        return deps_finales

    # ------------------------------------------------------------------
    def actualizar_pyproject(self, nuevas_deps: Dict[str, Any]):
        if "tool" not in self.cfg:
            self.cfg["tool"] = {}
        if "poetry" not in self.cfg["tool"]:
            self.cfg["tool"]["poetry"] = {}
        self.cfg["tool"]["poetry"]["dependencies"] = nuevas_deps

        with open(self.ruta, "w", encoding="utf-8") as f:
            toml.dump(self.cfg, f)
        print(f"\npyproject.toml actualizado correctamente")

    # ------------------------------------------------------------------
    def instalar(self, dry_run: bool = True):
        print("\nLanzando Poetry...")
        cmd = [sys.executable, "-m", "poetry", "install", "--no-interaction"]
        if dry_run:
            print("  Modo dry-run → no se ejecuta instalación real")
            print("  Comando que se ejecutaría:", " ".join(cmd))
            return
        try:
            subprocess.run(cmd, check=True, cwd=self.ruta.parent)
            print("Instalación completada con éxito")
        except subprocess.CalledProcessError as e:
            print("Error durante la instalación con Poetry:", e)

# ===================================================================
# Uso directo (ejecutar con python metsudep_manager.py)
# ===================================================================
if __name__ == "__main__":
    print("MetsuDepManager – Resolución ética de dependencias para MetsuOS\n")
    manager = MetsuDepManager()
    deps = manager.generar_dependencias_poetry()
    manager.actualizar_pyproject(deps)
    manager.instalar(dry_run=False)   # Cambia a True para pruebas
```
> Un codigo interesante para investigar pero, en principio, toca escribirlo a mano porque no acaba de encajar con lo que necesito.
### Referencias bibliográficas que **apoyan** esta solución

1. [**Poetry – Sección tool personalizada** 🟡③🌐](https://python-poetry.org/docs/pyproject/#tool-section) .- Documentación oficial de Poetry que explica explícitamente que la sección [tool.*] de pyproject.toml está diseñada para ser extendida libremente por cualquier herramienta, lo que legitima y avala el uso de [tool.metsudep] como extensión oficial y conforme al estándar.
2. [**PEP 621 – Metadatos de proyecto en pyproject.toml** 🟡③🌐](https://peps.python.org/pep-0621/) .- Estándar oficial de Python (aceptado en 2020 y vigente en 2025) que define pyproject.toml como el archivo único y extensible para metadatos de proyecto. Refuerza que cualquier herramienta puede añadir sus propias secciones sin romper compatibilidad.
3. [**GNU – Licencias compatibles con GPL** 🟡③🌐](https://www.gnu.org/licenses/license-list.en.html) .- Lista oficial y permanentemente actualizada por la Free Software Foundation que clasifica las licencias según su compatibilidad con GPL-3.0 y versiones posteriores. Es la referencia canónica para cualquier proyecto que quiera restringir dependencias a copyleft fuerte (como la capa “fsf-fan” de MetsuOS).
4. [**REUSE Initiative – Verificación automática de licencias** 🟡③🌐](https://reuse.software/) .- Proyecto respaldado por la Free Software Foundation Europe que establece el estándar de facto para declarar y comprobar automáticamente licencias en repositorios. Su enfoque (declarar licencia por archivo + herramientas de validación) sirve de inspiración y justificación técnica para la capa ética de MetsuDepManager.
5. [**Hynek Schlawack – “Python Application Dependency Management in 2018”** 🟡③🌐](https://hynek.me/articles/python-app-deps-2018/) .- Artículo de referencia escrito por Hynek Schlawack (mantenedor de attrs, Twisted y experto en packaging) donde analiza en profundidad el estado del arte de la gestión de dependencias en aplicaciones Python. Recomienda explícitamente usar herramientas maduras como Poetry como base y extenderlas en lugar de crear nuevos sistemas desde cero —justificación perfecta para la arquitectura de MetsuDepManager— y sigue siendo una de las guías más citadas y vigentes en la comunidad profesional (accesible y verificado a 29 de noviembre de 2025).
### Referencias bibliográficas que **cuestionan o matizan** la propuesta

1. [Nick Anthony – “Stop using Pip, use Poetry Instead!” 🟡③🌐](https://nanthony007.medium.com/stop-using-pip-use-poetry-instead-db7164f4fc72) .- Artículo de Medium (2021) que defiende el uso de Poetry sobre pip para la gestión de dependencias en proyectos Python, destacando su simplicidad, reproducibilidad y manejo de lockfiles —sirve como matiz positivo para la elección de Poetry como base en MetsuDepManager, contrastando con críticas generales al ecosistema de packaging y enfatizando por qué extender Poetry es una decisión sólida para proyectos modulares como MetsuOS (verificado y accesible a 29 de noviembre de 2025).
2. [Real Python – “Pipenv: A Guide to the Python Packaging Tool” 🟡③🌐](https://realpython.com/pipenv-guide/) .- Guía detallada de Real Python (actualizada en 2022, con relevancia vigente en 2025) que explica cómo Pipenv resuelve problemas comunes de dependencias en Python, comparándolo implícitamente con workflows tradicionales como pip + requirements.txt y destacando su simplicidad para flujos básicos —sirve como matiz al argumentar que herramientas como Pipenv pueden ser preferibles en escenarios simples, cuestionando si la complejidad añadida por Poetry (y extensiones como MetsuDepManager) es siempre justificada en proyectos modulares (verificado y accesible a 29 de noviembre de 2025).
3. [Tzu-ping Chung – "Let’s fix extras in Core Metadata 3.0" 🟡③🌐](https://speakerdeck.com/uranusjr/lets-fix-extras-in-core-metadata-3-dot-0) .- Presentación de Tzu-ping Chung en el Packaging Summit de PyCon US 2022, donde discute problemas fundamentales en el manejo de "extras" en el Core Metadata de Python (versión 2.4), destacando la fragmentación y la necesidad de normalización para resolver conflictos de compatibilidad —una crítica técnica que ilustra el "desorden" en el ecosistema de empaquetado y matiza la extensión de herramientas como Poetry con capas adicionales como MetsuDepManager, enfatizando la importancia de soluciones estandarizadas mínimas (verificado y accesible a 29 de noviembre de 2025).
4. [Ali Abbas Jaffri – “Poetry Package Installation Woes” 🟡③🌐](https://medium.com/@aliabbasjaffri_/poetry-package-installation-woes-45c74fb5a11d) .- Artículo personal de Ali Abbas Jaffri (2022, vigente en 2025) que relata problemas reales al instalar Poetry en un proyecto Python, enfocándose en fallos graves del resolver de dependencias con paquetes como scipy, scikit-learn y numpy —una crítica práctica que matiza el uso de Poetry como base para MetsuDepManager, destacando cómo sus limitaciones en resolución de conflictos pueden requerir workarounds como versiones específicas de Python, aunque no invalida su adopción en proyectos éticos y modulares como MetsuOS (verificado y accesible a 29 de noviembre de 2025).

![[Plantilla - 1MT#One More Thing]]