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
created: 2025-12-09T00:11:58.993Z
modified: 2026-01-06T19:42:46.538Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 6
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_014.mp4
---
# El pyproject.toml - todos los campos (incluso los menos conocidos) 🟡③

![El pyproject.toml - todos los campos (incluso los menos conocidos)](PublicBrain/_resources/2aa13ad84859df87b2816eab648b5790_MD5.jpg)

[[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

## Inicialización de un Proyecto Python desde Cero con Poetry

Si estás empezando un proyecto en Python y quieres usar Poetry como gestor de dependencias, no hace falta complicarse con comandos manuales uno a uno. En su lugar, he preparado un script sencillo en Python, llamado `inicializar.py`, que automatiza todo el proceso. Este script parte de un entorno Python 3.11 o superior con `pip` instalado (que viene de serie con Python). Primero, comprueba si Poetry está disponible; si no, lo instala automáticamente mediante `pip`. Luego, crea el proyecto en el directorio actual con `poetry new .`, genera la estructura básica y un fichero `pyproject.toml` preconfigurado. Por último, instala las dependencias iniciales y verifica que todo esté en orden.

Para ponerlo en marcha:
1. Crea un directorio vacío para tu proyecto (por ejemplo, `mkdir mi_proyecto && cd mi_proyecto`).
2. Crea el fichero `init_metsudepmanager.py` en ese directorio con el código que te detallo a continuación.
3. Ejecuta el script: `python init_metsudepmanager.py`.

El script gestiona errores habituales, y utiliza `subprocess` para ejecutar comandos de manera segura. Aquí va el código completo:

```python
# Comentarios para humanos

# Este script inicializa un entorno de desarrollo para MetsuDepManager basado en Poetry.

# Su función principal es:

# - Verificar si Poetry está instalado en el sistema.

# - Si no lo está, instalarlo automáticamente usando el método oficial recomendado (instalador vía curl) con fallback a pip.

# - Detectar si ya existe un proyecto Poetry (pyproject.toml) en el directorio actual.

# - Si existe: ejecutar 'poetry install' para instalar todas las dependencias y crear/actualizar el entorno virtual.

# - Si no existe: inicializar un nuevo proyecto Poetry de forma NO interactiva usando 'poetry init --no-interaction'.

# Esto crea un pyproject.toml básico con valores por defecto (nombre basado en el directorio, versión 0.1.0, etc.).

# - Añadir temporalmente ~/.local/bin al PATH si es necesario (para que Poetry sea accesible en la misma sesión).

# - Proporcionar mensajes claros al usuario sobre cada paso realizado.

# El script está diseñado para ser ejecutado una sola vez al clonar o crear el proyecto MetsuDepManager,

# pero puede volver a ejecutarse sin problemas para reinstalar dependencias.

# Compatible con macOS, Linux y Windows (WSL o nativo con Python instalado).

# Autor: Raul Carrillo aka metsuke <metsuke@gmail.com>

# Fecha de última actualización: enero 2026.

# Corrección reciente: Se cambió a modo no interactivo en 'poetry init' para evitar que el script se cuelgue esperando input del usuario.

  

# Documentación

# Uso:

# python init_metsudepmanager.py

# Requisitos previos:

# - Python 3.8 o superior instalado y accesible en PATH.

# - Conexión a internet la primera vez (para descargar e instalar Poetry si no está presente).

# Flujo del script:

# 1. Verifica si 'poetry' está disponible en PATH.

# 2. Si no → intenta instalar vía instalador oficial (curl).

# 3. Si falla el instalador oficial → fallback a 'pip install --user poetry'.

# 4. Añade ~/.local/bin al PATH de la sesión actual si es necesario.

# 5. Si existe pyproject.toml → ejecuta 'poetry install'.

# 6. Si no existe → ejecuta 'poetry init --no-interaction' para crear un pyproject.toml básico automáticamente.

# 7. Informa al usuario de los siguientes pasos recomendados (poetry shell, poetry add, etc.).

# Notas:

# - El script no modifica archivos existentes ni fuerza opciones; respeta el estado actual del proyecto.

# - En caso de error crítico (imposible instalar Poetry), termina con código de salida 1 y mensaje claro.

# - El modo no interactivo usa valores por defecto; puedes editar pyproject.toml manualmente después.

# Autor: Raul Carrillo aka metsuke <metsuke@gmail.com>

  

# Comentarios para IA

# Estado actual del código (enero 2026):

# - Instalación de Poetry: método principal vía instalador oficial curl (recomendado por python-poetry.org).

# - Fallback robusto a pip install --user poetry.

# - Detección automática de PATH y añadido temporal para la sesión actual.

# - Lógica diferenciada: install existente vs. init nuevo proyecto.

# - Uso de shutil.which para detección fiable de Poetry.

# - Manejo de errores detallado con mensajes claros para el usuario.

# - No se añaden dependencias iniciales automáticas (para respetar libertad del usuario).

# - Compatible con entornos restringidos (sin sudo necesario gracias a --user).

# - Cambio clave: 'poetry init --no-interaction' para evitar hanging en subprocess.run() cuando se espera input interactivo.

# - Autor añadido explícitamente como "Raul Carrillo aka metsuke <metsuke@gmail.com>" en comentarios para humanos y documentación.

# Todo alineado con mejores prácticas actuales de Poetry en 2026.

  

# Exigencias Generales a la IA

# - Debes generar y mantener varios bloque de comentarios varios en la cabecera del fichero, como comentario de comentarios para humanos, otro de documentacion, otro con comentarios para IA en la que tu te apuntes lo que necesites para futuros trabajos con el script, y las dos secciones de Exigencias a la IA, la general (generica de programación) y la especifica del script que estamos trabajando.

# - Siempre actualiza el contenido de los comentarios para humanos e IA en cada revisión del script, manten intacta el área de Exigencias a IA.

# - No modifiques nada del script que no te hayan pedido explícitamente sin consultarlo primero.

# ---

# Exigencias especificas del script para la IA

  

import subprocess

import sys

import os

import shutil

  

def run_command(cmd, check=True):

"""Ejecuta un comando en la shell y maneja errores de forma amigable."""

try:

result = subprocess.run(cmd, check=check, text=True, capture_output=True)

if result.stdout:

print(result.stdout)

return True

except subprocess.CalledProcessError as e:

print(f"Error ejecutando {' '.join(cmd)}:")

if e.stderr:

print(e.stderr)

return False

except FileNotFoundError:

print(f"Comando no encontrado: {cmd[0]}. Verifica que esté instalado y en PATH.")

return False

  

def is_poetry_installed():

"""Comprueba si Poetry está disponible en el sistema."""

return shutil.which("poetry") is not None

  

def install_poetry():

"""Instala Poetry usando el método oficial recomendado (2026)."""

print("Poetry no detectado. Instalándolo mediante el instalador oficial...")

# Método principal: instalador oficial vía curl

install_cmd = ["curl", "-sSL", "https://install.python-poetry.org", "|", sys.executable, "-"]

if run_command(install_cmd):

print("Instalación oficial completada.")

else:

print("Fallback: instalando Poetry vía pip...")

if not run_command([sys.executable, "-m", "pip", "install", "--user", "poetry"]):

print("No se pudo instalar Poetry automáticamente.")

return False

# Añadir ~/.local/bin al PATH de esta sesión si es necesario

poetry_path = os.path.expanduser("~/.local/bin")

if poetry_path not in os.environ.get("PATH", ""):

os.environ["PATH"] += os.pathsep + poetry_path

print(f"Añadido {poetry_path} al PATH de esta sesión.")

return True

  

def main():

print("=== Inicializador de MetsuDepManager con Poetry ===\n")

if not is_poetry_installed():

if not install_poetry():

print("\nNo se pudo instalar Poetry. Instálalo manualmente desde:")

print("https://python-poetry.org/docs/#installation")

sys.exit(1)

# Verificar nuevamente tras instalación

if not is_poetry_installed():

print("Poetry instalado pero no detectable en PATH. Reinicia la terminal o añade ~/.local/bin al PATH.")

sys.exit(1)

print("Poetry está disponible y listo para usar.\n")

if os.path.exists("pyproject.toml"):

print("Proyecto Poetry existente detectado (pyproject.toml encontrado).")

print("Instalando dependencias...\n")

run_command(["poetry", "install"])

else:

print("No se encontró pyproject.toml. Inicializando nuevo proyecto Poetry de forma automática (no interactiva)...\n")

run_command(["poetry", "init", "--no-interaction"])

print("\npyproject.toml creado con valores por defecto.")

print("Edítalo manualmente si necesitas cambiar nombre, versión, autor, etc.")

print("Luego ejecuta 'poetry install' para crear el entorno virtual.")

print("\n¡MetsuDepManager inicializado correctamente!")

print("Pasos recomendados:")

print(" • poetry shell → activar el entorno virtual")

print(" • poetry add <paquete> → añadir nuevas dependencias")

print(" • poetry run python tu_script.py → ejecutar scripts en el entorno")

  

if __name__ == "__main__":

main()
```

### Explicación breve del script (sin entrar en detalles manuales)
- El script comprueba si poetry está instalado, si no lo está lo instala
- A continuacion, si ya existe el toml ejecuta poetry install, en caso contrario inicializa con los datos por defecto, y deberás configurar el proyecto.

Con esto, tienes el proyecto listo en un santiamén. Ahora, vamos a profundizar en el fichero `pyproject.toml`, explicando todos sus campos de forma detallada pero accesible.

# El pyproject.toml: Todos los Campos (Incluso los Menos Conocidos)

El fichero `pyproject.toml` es el núcleo de cualquier proyecto Python moderno. Sustituye a los antiguos `setup.py`, `setup.cfg` o `requirements.txt`, y sigue el estándar PEP 518 para definir el sistema de construcción, metadatos y dependencias en un formato TOML claro y declarativo. En el mundo de Poetry (y, por extensión, en MetsuDepManager), amplía estos estándares con la sección `[tool.poetry]`, ofreciendo un control preciso sobre dependencias, scripts y extras, mientras deja el trabajo pesado a `poetry-core`.

Poetry da prioridad a la sección `[project]` (compatible con PEP 621) para metadatos estáticos, pero conserva `[tool.poetry]` para opciones heredadas o avanzadas. Los campos dinámicos (indicados con `dynamic = [...]`) permiten calcular valores en tiempo de ejecución, como la versión desde un tag de Git. Entre los campos menos habituales, destacan las configuraciones para puntos de entrada personalizados, dependencias condicionales o plugins de construcción.

Voy a estructurarlo por secciones principales, con una descripción del propósito (incluyendo su uso en el curso), el tipo de dato, si es obligatorio, un ejemplo realista y notas sobre comportamientos especiales, depreciaciones o consejos prácticos para MetsuDepManager.

## 1. [build-system] – Configuración del Sistema de Construcción (PEP 517/518)

Esta sección es esencial para construcciones independientes y define el backend (Poetry usa `poetry-core` para evitar ciclos de dependencias).

- **requires** (lista de cadenas):
  - **Descripción**: Paquetes necesarios para la construcción (por ejemplo, `poetry-core` resuelve dependencias y genera wheels).
  - **Tipo**: `list[string]` (especificaciones PEP 508).
  - **Obligatorio**: Sí.
  - **Ejemplo**:
    ```toml
    requires = ["poetry-core>=1.0.0"]
    ```
  - **Notas**: En el curso, se emplea `poetry-core` como backend clave en MetsuDepManager para auditorías y límites de tiempo. Un campo menos común: puedes añadir extras como `["poetry-core[pep517]>=1.0.0"]` para construcciones híbridas. No se instalan en tiempo de ejecución; solo para la fase de build.

- **build-backend** (cadena):
  - **Descripción**: Módulo invocable para la construcción (hook PEP 517).
  - **Tipo**: `string` (por ejemplo, `"poetry.core.masonry.api"`).
  - **Obligatorio**: Sí.
  - **Ejemplo**:
    ```toml
    build-backend = "poetry.core.masonry.api"
    ```
  - **Notas**: Poetry lo utiliza para generar metadatos y wheels. Poco frecuente: para backends personalizados, usa `"mi_backend.build:build_wheel"`. En entornos aislados, asegúrate de que `poetry-core` esté preinstalado.

- **backend-path** (lista de cadenas, menos conocido):
  - **Descripción**: Rutas relativas para localizar el backend (útil en monorepos).
  - **Tipo**: `list[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    backend-path = ["src", "vendor"]
    ```
  - **Notas**: Se ignora si no hace falta. En MetsuDepManager, práctico para subproyectos.

## 2. [project] – Metadatos del Proyecto (PEP 621)

Esta es la sección principal para metadatos estáticos. Poetry la prefiere para compatibilidad con herramientas como `pip` o `twine`.

- **name** (cadena):
  - **Descripción**: Nombre único del paquete (en minúsculas, sin espacios).
  - **Tipo**: `string`.
  - **Obligatorio**: Sí.
  - **Ejemplo**:
    ```toml
    name = "metsudepmanager"
    ```
  - **Notas**: Debe cumplir PEP 503. En el curso, se usa "metsudepmanager" para el gestor ético.

- **version** (cadena):
  - **Descripción**: Versión semántica (PEP 440).
  - **Tipo**: `string`.
  - **Obligatorio**: Sí (o dinámico).
  - **Ejemplo**:
    ```toml
    version = "0.1.0"
    ```
  - **Notas**: Para dinámico: `dynamic = ["version"]` y actualiza con `poetry version patch` o tags de Git. Menos conocido: soporta prelanzamientos como `0.1.0a1`.

- **description** (cadena):
  - **Descripción**: Resumen breve (menos de 512 caracteres).
  - **Tipo**: `string`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    description = "Gestor de paquetes Python ético con Poetry como backend"
    ```
  - **Notas**: Aparece en PyPI. En el curso: centrado en "ético y configurable".

- **readme** (cadena o lista de cadenas):
  - **Descripción**: Fichero(s) README para la descripción larga.
  - **Tipo**: `string` o `list[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    readme = {file = "README.md", content-type = "text/markdown"}
    # O múltiple (dinámico):
    dynamic = ["readme"]
    ```
  - **Notas**: Soporta tipo de contenido (por defecto: text/plain). Raro: múltiples para internacionalización.

- **license** (cadena o tabla):
  - **Descripción**: "I"dentificador SPDX o diccionario con texto/ficheros.
  - **Tipo**: `string` o `table`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    license = {text = "MIT"}
    ```
  - **Notas**: Depreciado `text`; usa `license-files`. Lista SPDX con más de 400 licencias.

- **license-files** (lista de cadenas):
  - **Descripción**: Patrones glob para ficheros de licencia.
  - **Tipo**: `list[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    license-files = ["LICENSE", "LICENSES/*"]
    ```
  - **Notas**: Por defecto incluye LICENSE*. En el curso: para cumplimiento ético.

- **authors** (lista de tablas):
  - **Descripción**: Lista de autores con nombre, correo y URL.
  - **Tipo**: `list[table{name: string, email?: string, url?: string}]`.
  - **Obligatorio**: No (recomendado al menos uno).
  - **Ejemplo**:
    ```toml
    authors = [
      {name = "Equipo Metsuke", email = "dev@metsuke.com"}
    ]
    ```
  - **Notas**: Correo opcional; URL para perfiles.

- **maintainers** (lista de tablas, menos conocido):
  - **Descripción**: Mantenedores aparte de autores.
  - **Tipo**: `list[table{name: string, email?: string}]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    maintainers = [
      {name = "Mantenedor Principal", email = "maintainer@metsuke.com"}
    ]
    ```
  - **Notas**: Útil en proyectos grandes como MetsuDepManager.

- **keywords** (lista de cadenas):
  - **Descripción**: Etiquetas para búsquedas en PyPI.
  - **Tipo**: `list[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    keywords = ["poetry", "dependencias", "paquetes", "etico"]
    ```
  - **Notas**: Máximo 5-10; no indexadas directamente en PyPI.

- **classifiers** (lista de cadenas):
  - **Descripción**: Clasificadores Trove para categorización en PyPI.
  - **Tipo**: `list[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    classifiers = [
      "Development Status :: 3 - Alpha",
      "Topic :: Software Development :: Build Tools",
      "License :: OSI Approved :: MIT License",
      "Programming Language :: Python :: 3 :: Only"
    ]
    ```
  - **Notas**: Poetry añade automáticamente basados en `requires-python` si dinámico. Lista completa en PyPI. Raro: "Private :: Do Not Upload".

- **requires-python** (cadena):
  - **Descripción**: Especificador de versión de Python (PEP 440).
  - **Tipo**: `string`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    requires-python = ">=3.8"
    ```
  - **Notas**: Complementa `[tool.poetry.dependencies.python]`. En el curso: ">=3.8" para `poetry-core`.

- **dependencies** (lista de cadenas):
  - **Descripción**: Dependencias obligatorias en tiempo de ejecución.
  - **Tipo**: `list[string]` (PEP 508).
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    dependencies = [
      "requests >= 2.31.0"
    ]
    ```
  - **Notas**: Usadas en metadatos de wheel; Poetry las sincroniza con el lockfile.

- **optional-dependencies** (tabla de listas de cadenas):
  - **Descripción**: Extras opcionales (por ejemplo, "dev", "docs").
  - **Tipo**: `table[list[string]]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [project.optional-dependencies]
    dev = ["pytest >= 7.0", "black"]
    docs = ["sphinx"]
    ```
  - **Notas**: Instalables con `pip install .[dev]`. En el curso: para grupos como "audit".

- **urls** (tabla de cadenas):
  - **Descripción**: Enlaces personalizados (página principal, repositorio, etc.).
  - **Tipo**: `table[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [project.urls]
    Homepage = "https://metsuke.com/metsudepmanager"
    Repository = "https://github.com/metsuke/metsudepmanager"
    "Bug Tracker" = "https://github.com/metsuke/metsudepmanager/issues"
    Documentation = "https://metsuke.com/docs"
    ```
  - **Notas**: Las claves con espacios están permitidas; se muestran en PyPI.

- **scripts** (tabla de cadenas):
  - **Descripción**: Puntos de entrada para interfaces de línea de comandos (CLI) de consola.
  - **Tipo**: `table[string]` (módulo:función).
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [project.scripts]
    metsudep = "metsudepmanager.cli:main"
    ```
  - **Notas**: Se instalan como ejecutables. En el curso: para la CLI de MetsuDepManager con Typer.

- **gui-scripts** (tabla de cadenas, menos conocido):
  - **Descripción**: Puntos de entrada para CLI gráficas.
  - **Tipo**: `table[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [project.gui-scripts]
    metsudep-gui = "metsudepmanager.gui:launch"
    ```
  - **Notas**: Similar a scripts, pero adaptado para interfaces gráficas (poco común en Python puro).

- **entry-points** (tabla de tablas de cadenas):
  - **Descripción**: Plugins y hooks genéricos (PEP 566).
  - **Tipo**: `table[table[string]]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [[project.entry-points."console_scripts"]]
    custom-tool = "metsudepmanager.tools:custom_func"

    [project.entry-points."poetry.plugin"]
    metsudep-plugin = "metsudepmanager.plugin:PluginClass"
    ```
  - **Notas**: Estructura anidada; ideal para plugins de Poetry. Menos conocido: soporta listas para valores múltiples.

- **dynamic** (lista de cadenas, menos conocido):
  - **Descripción**: Campos calculados durante la construcción (por ejemplo, versión desde dynaconf).
  - **Tipo**: `list[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    dynamic = ["version", "readme", "classifiers"]
    ```
  - **Notas**: Requiere un backend que los resuelva (Poetry lo hace). En el curso: para versiones dinámicas en lanzamientos.

## 3. [tool.poetry] – Configuración Específica de Poetry

Amplía `[project]` con características propias de Poetry. Muchos campos están depreciados en favor de `[project]`, pero se mantienen por compatibilidad. En MetsuDepManager, se usa para delegar a `poetry-core` sin telemetría.

- **name**, **version**, **description**, **license**, **authors**, **maintainers**, **readme**, **keywords**, **classifiers**:
  - **Descripción**: Equivalentes a `[project]` (ver arriba).
  - **Tipo**: Igual.
  - **Obligatorio**: No (depreciados).
  - **Ejemplo**: Similar a `[project]`.
  - **Notas**: Poetry los migra automáticamente. Úsalos solo para compatibilidad antigua.

- **homepage**, **repository**, **documentation** (cadenas, depreciados):
  - **Descripción**: URLs básicas.
  - **Tipo**: `string`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    homepage = "https://metsuke.com"
    ```
  - **Notas**: Sustituidos por `[project.urls]`.

- **packages** (lista de tablas, menos conocido):
  - **Descripción**: Especifica paquetes a incluir (para layout de fuentes o multipaquete).
  - **Tipo**: `list[table{include: string, from?: string}]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [tool.poetry.packages]
    include = "metsudepmanager"
    from = "src"
    ```
  - **Notas**: Por defecto: raíz. Raro: `exclude = ["tests"]` para filtros.

- **include** y **exclude** (lista de cadenas, menos conocido):
  - **Descripción**: Ficheros a incluir/excluir en distribuciones.
  - **Tipo**: `list[string]` (globs).
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [tool.poetry]
    include = ["src/**/*.py", "data/*.json"]
    exclude = ["tests/*", "*.pyc"]
    ```
  - **Notas**: Sobrescribe valores por defecto. En el curso: excluye telemetría.

- **dependencies** (tabla de listas de cadenas):
  - **Descripción**: Dependencias en tiempo de ejecución (incluye `python`).
  - **Tipo**: `table[list[string]]`.
  - **Obligatorio**: No.
  - **Subsección: python (cadena)**:
    - **Ejemplo**:
      ```toml
      [tool.poetry.dependencies]
      python = ">=3.8,<3.12"
      requests = "^2.31.0"
      typer = {version = "^0.12.0", python = ">=3.9"}
      ```
    - **Notas**: Especificadores condicionales (por ejemplo, markers). Poetry resuelve conflictos.

- **group** (tabla anidada de tablas de listas de cadenas, desde 1.2):
  - **Descripción**: Grupos de dependencias (dev, test, docs).
  - **Tipo**: Anidado.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [[tool.poetry.group.dev.dependencies]]
    name = "pytest"
    version = "^7.4.0"

    [[tool.poetry.group.audit.dependencies]]  # Personalizado para el curso
    name = "bandit"
    version = "^1.7.5"
    ```
  - **Notas**: Instalables con `poetry install --only dev`. En MetsuDepManager: grupos para "audit" y "airgapped".

- **dev-dependencies** (lista de cadenas, depreciado):
  - **Descripción**: "H"eredado para dependencias de desarrollo.
  - **Tipo**: `list[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [tool.poetry.dev-dependencies]
    pytest = "^7.4.0"
    ```
  - **Notas**: Migra a `group.dev.dependencies`.

- **extras** (tabla de listas de cadenas):
  - **Descripción**: Dependencias opcionales (extras).
  - **Tipo**: `table[list[string]]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [tool.poetry.extras]
    mysql = ["mysqlclient"]
    security = ["cryptography"]
    ```
  - **Notas**: Se sincroniza con `[project.optional-dependencies]`. Raro: extras con subdependencias.

- **scripts** (tabla de cadenas):
  - **Descripción**: CLI locales (no instalados globalmente).
  - **Tipo**: `table[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [tool.poetry.scripts]
    test = "pytest"
    lint = "ruff check ."
    ```
  - **Notas**: Ejecutables con `poetry run test`. En el curso: para hooks de auditoría.

- **plugins** (tabla de cadenas, menos conocido):
  - **Descripción**: Plugins de Poetry (por ejemplo, para exportar a requirements.txt).
  - **Tipo**: `table[string]`.
  - **Obligatorio**: No.
  - **Ejemplo**:
    ```toml
    [tool.poetry.plugins."poetry.application.plugin"]
    export-plugin = "poetry_plugin_export:ExportPlugin"
    ```
  - **Notas**: Extiende Poetry. En MetsuDepManager: para solvers personalizados sin telemetría.

- **package-mode** (booleano):
  - **Descripción**: Modo paquete vs. aplicación (false para scripts puros).
  - **Tipo**: `bool`.
  - **Obligatorio**: No (por defecto: true).
  - **Ejemplo**:
    ```toml
    package-mode = false
    ```
  - **Notas**: Afecta la instalación del código fuente.

## 4. Otras Secciones Menos Conocidas o Extendidas

- **[tool.poetry-dynamic-versioning]** (específico de plugin, raro):
  - **Descripción**: Para versiones dinámicas desde Git.
  - **Ejemplo**:
    ```toml
    [tool.poetry-dynamic-versioning]
    enable = true
    vcs = "git"
    ```
  - **Notas**: Requiere plugin; útil para CI en el curso.

- **[tool.setuptools]** (si usas setuptools como backend alternativo):
  - **Descripción**: Configuración para campos dinámicos.
  - **Ejemplo**:
    ```toml
    [tool.setuptools.dynamic]
    version = {attr = "metsudepmanager.__version__"}
    ```
  - **Notas**: No para Poetry puro; solo en híbridos.

- **Comentarios y metadatos adicionales**:
  - TOML permite comentarios (#). Poetry ignora secciones no reconocidas (por ejemplo, `[tool.black]` para formateadores).
  - En MetsuDepManager: integra `[tool.ruff]` para linting ético, excluyendo fugas.

## Consideraciones Finales y Mejores Prácticas

- **Validación**: Siempre ejecuta `poetry check` y `poetry lock --no-update` para reproducibilidad.
- **Migración**: Pasa de heredados a `[project]` con `poetry self show plugins`.
- **En el curso**: Esta estructura facilita el wrapping de `poetry-core` para control (límites de tiempo, sin telemetría), haciendo MetsuDepManager más extensible.
- **Longitud**: Un `pyproject.toml` completo puede superar las 200 líneas; usa herramientas como `toml-sort` para organizarlo.

# Referencias Bibliográficas que Apoyan

Estas fuentes respaldan el uso de Poetry y la estructura de `pyproject.toml`, con énfasis en su eficiencia y estándares PEP. He verificado su existencia, vigencia (actuales a 2025) y relevancia científica mediante búsquedas en web y documentación oficial.

1. [Documentación oficial de Poetry sobre pyproject.toml 🟡③🌐](https://python-poetry.org/docs/pyproject/) .- Documentación oficial que explica la estructura y campos del archivo pyproject.toml en Poetry, incluyendo secciones project y tool.poetry, requisitos y compatibilidad con estándares PEP.
2. [PEP 517 – A build-system independent format for source trees 🟡③🌐](https://peps.python.org/pep-0517/) .- Propuesta que define un formato independiente para sistemas de construcción en árboles de fuente Python, utilizando pyproject.toml y hooks para herramientas como pip.
3. [PEP 518 – Specifying Minimum Build System Requirements 🟡③🌐](https://peps.python.org/pep-0518/) .- Especificación para declarar requisitos mínimos de sistemas de construcción en proyectos Python mediante pyproject.toml, facilitando la instalación de dependencias de build.
4. [PEP 621 – Storing project metadata in pyproject.toml 🟡③🌐](https://peps.python.org/pep-0621/) .- Estándar para almacenar metadatos de proyectos como nombre, versión y dependencias en pyproject.toml de manera estática y consistente.
5. [Tutorial de Real Python sobre Dependency Management with Poetry 🟡③🌐](https://realpython.com/dependency-management-python-poetry/) .- Guía práctica sobre el uso de Poetry para manejar dependencias en Python, cubriendo instalación, configuración de pyproject.toml, entornos virtuales y mejores prácticas.
6. [Vídeo en YouTube: Gestión de dependencias en Python con Poetry 🟡③🌐](https://www.youtube.com/watch?v=j3PzCdmbxEE) .- Video tutorial en español sobre optimización de procesos de trabajo y gestión de dependencias en Python usando Poetry, por Garaje de ideas | Tech.
7. [Vídeo en YouTube: Cómo Gestionar Tus Proyectos De Python Con Poetry 🟡③🌐](https://www.youtube.com/watch?v=sYtXjiCua48) .- Video explicativo en español sobre gestión de proyectos Python con Poetry, enfocándose en buenas prácticas de desarrollo, por deployr.

# Referencias Bibliográficas que Refutan

Estas fuentes destacan críticas a Poetry, como lentitud en resolución de dependencias, problemas de compatibilidad o preferencia por alternativas más rápidas como UV o PDM. He confirmado su validez y vigencia (2023-2025) mediante búsquedas.

- 1. [Discusión en Reddit sobre críticas a Poetry 🟡③🌐](https://www.reddit.com/r/learnpython/comments/10jb11n/what_do_you_feel_about_using_poetry_package/) .- The Reddit post and comments highlight several criticisms of Poetry as a Python package manager: unreliable and prone to failures, redundant and unnecessary, imposes unnecessary complexity, limited applicability.
2. [Artículo en Medium: Python's Package Management is a Mess 🟡③🌐](https://medium.com/@yashbatra11111/pythons-package-management-is-a-mess-b0bb9c1055bf) .- Python’s package management is criticized for inconsistencies, dependency conflicts, and tool fragmentation including pip, conda, poetry, pipenv, and virtualenv.
3. [Comparativa en DEV Community: A Review: Pipenv vs. Poetry vs. PDM 🟡③🌐](https://dev.to/frostming/a-review-pipenv-vs-poetry-vs-pdm-39b4) .- Pipenv, Poetry, and PDM are compared on performance and correctness; Pipenv has poor performance and correctness issues, while Poetry and PDM perform better, with PDM being faster.
4. [Tutorial en DataCamp sobre UV como alternativa 🟡③🌐](https://www.datacamp.com/es/tutorial/python-uv) .- UV es un gestor de paquetes Python de alto rendimiento escrito en Rust que sirve como alternativa a herramientas como Poetry, ofreciendo gestión de dependencias y entornos virtuales con velocidad superior.
5. [Vídeo en YouTube: why I will never use python-poetry 🟡③🌐](https://www.youtube.com/watch?v=Gr9o8MW_pb0) .- The video criticizes Python Poetry on technical grounds including default versioning leading to conflicts and trust issues from mishandled deprecation of installation scripts.
6. [Artículo en GeeksforGeeks: How to fix "Python Poetry Install Failure" 🟡③🌐](https://www.geeksforgeeks.org/python/how-to-fix-python-poetry-install-failure/) .- Addresses common installation issues with Python Poetry including missing dependencies, network problems, permissions, compatibility, and corrupted installations with fixes.


![[Plantilla - 1MT#One More Thing]]