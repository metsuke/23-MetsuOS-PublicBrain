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
created: 2025-12-01T09:00:15.625Z
modified: 2025-12-05T18:05:05.202Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_004.mp4
---
# Requisitos Previos para el Curso de MetsuDepManager - Prepárate sin Complicaciones 🟡③


![Requisitos Previos para el Curso de MetsuDepManager - Prepárate sin Complicaciones](PublicBrain/_resources/7ca926b2ca82e9120c0ce1718119fb0c_MD5.jpg)
[[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

Si estás a punto de sumergirte en el curso de Metsuke para crear MetsuDepManager —ese gestor de paquetes Python que pone la ética y la seguridad en el centro, usando Poetry como base—, lo primero es asegurarte de que tu setup no te frene. No te pido que seas un experto, solo que tengas lo básico para no atascarte en los primeros pasos. Piensa en esto como el calentamiento antes de una buena partida: rápido, efectivo y sin sorpresas. Vamos a repasarlo de forma sencilla, con trucos para que lo tengas listo en media hora.

## 1. Python: La Base Sólida que Necesitas

**Versión de Python requerida: ≥3.11 y <3.15**

```toml
[project]
name = "metsudepmanager"
requires-python = ">=3.11,<3.15"
```

Argumentación detallada en ... [[Decisión oficial sobre la versión de Python requerida por MetsuDepManager 🟡③]]

## 2. Lo Básico de Poetry: No Reinventes la Rueda

No hace falta ser un gurú, pero sí saber moverte con comandos como `poetry init` (para arrancar un proyecto), `poetry add paquete` (añadir dependencias), `poetry install` (montar todo) o `poetry lock` (fijar versiones para que sea repetible). Entiende el `pyproject.toml` como el manifiesto de tu proyecto y el lockfile como tu salvavidas contra sorpresas.

- **Por qué importa aquí:** MetsuDepManager es un wrapper sobre Poetry, así que si lo conoces, extenderlo será coser y cantar.
- **Repaso express:** Si hace meses que no lo usas, echa un ojo a la [docu oficial 🟡③🌐](https://python-poetry.org/docs/). Prueba: `poetry new prueba-rapida`, añade `requests` y corre `poetry install`. En 10 minutos, listo.
- **Extra para el curso:** Échale un vistazo a la API de Poetry (como `poetry.core`) —lo desgranamos después, pero adelantar te da ventaja.

## 3. Git en Sus Fundamentos: Versiona sin Sudor

Basta con lo esencial: `git init` para empezar un repo, `git add .` y `git commit -m "cambio claro"` para guardar, `git push` para subir y `git pull` para sincronizar. Conoce el `.gitignore` para esconder carpetas como `__pycache__` o venvs.

- **Razones prácticas:** El curso usa GitHub Actions para CI/CD, y clonarás el repo, crearás branches para features (como políticas éticas) y harás merges.
- **Si necesitas refrescar:** Instala Git (`git --version`) y crea una cuenta en GitHub. Prueba un repo de prueba: commit, push y branch. Configura tu identidad con `git config --global user.name "Tú"` y `git config --global user.email "tú@ejemplo.com"`.
- **Truco útil:** Usa branches descriptivas como `feature/motor-etico` para no liarte.

## 4. Línea de Comandos: Tu Aliada Diaria

Maneja lo básico: `cd` para cambiar de carpeta, `ls` para listar (o `dir` en Windows), `mkdir` para crear directorios y `echo "texto" > archivo.txt` para escribir rápido. En Linux/macOS, bash o zsh; en Windows, PowerShell o Git Bash.

- **Por qué no puedes evitarla:** El curso es puro terminal: comandos de MetsuDepManager, tests y debug de auditorías.
- **Si eres nuevo:** Practica con un cheat sheet. Usa VS Code con su terminal integrada para no saltar ventanas.
- **Plus:** Aprende `|` y `grep` para filtrar outputs —te salvará al chequear logs de Safety.

Con estos pilares, el módulo 1 (motivación y setup) será un paseo. El curso no es para absolutos principiantes, pero si cubres esto, disfrutarás cada paso hacia tu gestor personalizado. Invierte el tiempo ahora y agradece después.

## Referencias bibliográficas que apoyan estos requisitos previos

1. [Poetry Project (2025). *Poetry Documentation: "I"ntroduction*. 🟡③🌐](https://python-poetry.org/docs/) .- Documentación que confirma Python 3.9 o superior como requisito mínimo para Poetry, con soporte multiplataforma en Linux, macOS y Windows.
2. [Atlassian (2025). *How to Use Git: Tutorials, Workflows & Commands*. 🟡③🌐](https://www.atlassian.com/git) .- Guía completa sobre Git como sistema de control de versiones distribuido, cubriendo comandos básicos como commit, push, pull, branching y merging, workflows colaborativos y tutoriales para principiantes.
3. [Real Python (2024). *Build Command-Line Interfaces With Python's argparse*. 🟡③🌐](https://realpython.com/command-line-interfaces-python-argparse/) .- Tutorial que explica el uso de argparse para crear interfaces de línea de comandos en Python, incluyendo parsing de argumentos posicionales y opcionales, subcomandos, manejo de errores y generación de mensajes de ayuda.

## Referencias que refutan o matizan la necesidad de estos prerrequisitos estrictos

1. [Stack Overflow (2023). *How can I specify which Python version poetry should create venv?*. 🟡③🌐](https://stackoverflow.com/questions/66555963/how-can-i-specify-which-python-version-poetry-should-create-venv) .- Debate que muestra cómo Poetry puede usar versiones inferiores a 3.9 con pyenv o env use, matizando que el mínimo no es absoluto si se configura manualmente, aunque recomienda 3.9+ para estabilidad.
2. [W3Schools (2025). *Git Tutorial*. 🟡③🌐](https://www.w3schools.com/git/) .- Tutorial básico de Git que asume cero conocimientos previos, cubriendo desde instalación hasta workflows, sugiriendo que no se necesitan fundamentos avanzados para empezar en proyectos simples como un curso introductorio.
3. [HubSpot (2025). *An Intro to Git and GitHub for Beginners (Tutorial)*. 🟡③🌐](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners) .- Guía para principiantes que integra Git con GitHub sin requerir experiencia previa en terminal, enfocándose en PRs y branches básicas, cuestionando la necesidad de CLI profunda para flujos iniciales.


![[Plantilla - 1MT#One More Thing]]