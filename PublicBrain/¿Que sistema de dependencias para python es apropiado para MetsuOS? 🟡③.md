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
created: 2025-11-27T21:13:17.899Z
modified: 2025-11-27T22:33:44.671Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: MetsuDepManager.mp4
---
# ¿Que sistema de dependencias para python es apropiado para MetsuOS? 🟡③

![mosDepManager](PublicBrain/_resources/1f27a4f5935091d96a8f2f6c5aed74e8_MD5.jpg)

[[mosLib - El Corazón de MetsuOS  ⚫①]]

> OJO WIP
## Introducción

MetsuOS es un entorno modular, agnóstico al sistema operativo y construido completamente en Python sobre la biblioteca `mosLib`. Su diseño busca máxima inclusión, adaptabilidad y control ético-legal del software que se ejecuta en él. Por ello, las herramientas tradicionales de gestión de dependencias de Python (pip + requirements.txt, Poetry, PDM o Conda) resultan insuficientes: ninguna cubre de forma nativa la combinación de requisitos que MetsuOS necesita:

- Verificación automática de compatibilidad de licencias según las capas legales propias del proyecto (FSF-Fan, Community Layer, etc.).
- Priorización dinámica de paquetes.
- Dependencias opcionales y obligatorias claramente diferenciadas.
- Grupos de paquetes donde al menos uno debe estar presente.
- Versionado y selección de paquetes según el sistema operativo anfitrión.
- Integración con los módulos internos de MetsuOS (`mosLegalManager`, `mosTaskManager`, `mosSecurityManager`, etc.).

Por todo ello, la solución más robusta y coherente es crear un gestor de dependencias propio llamado **MetsuDepManager**, que toma como base el motor de resolución de Poetry (el más avanzado del ecosistema Python actual) pero lo extiende con toda la lógica específica de MetsuOS.

## Características principales de MetsuDepManager

- **Gestión avanzada de licencias**: consulta en tiempo real `mosLegalManager` y rechaza cualquier paquete cuya licencia sea incompatible con la capa activa del sistema.
- **Prioridades dinámicas**: los paquetes pueden declararse con prioridad alta, media o baja; en caso de conflicto o elección entre alternativas, `mosTaskManager` decide.
- **Dependencias obligatorias y opcionales** claramente marcadas.
- **Grupos “al menos uno obligatorio”** (útil para back-ends de gráficos, bases de datos, etc.).
- **Marcadores condicionales por sistema operativo** (Linux, Windows, macOS, Android vía Termux, etc.) y versiones específicas por host.
- **Instalación real mediante Poetry** como backend, lo que garantiza entornos reproducibles y resolución de conflictos de primer nivel.
- **Total integración** con el ecosistema `mosLib` (seguridad, red, tareas, IA, etc.).

## Ejemplo práctico de declaración (pyproject.toml extendido)

```toml
[tool.poetry.dependencies]
python = "^3.11"

# Dependencias obligatorias clásicas
numpy = "^1.26"

# Dependencias con metadatos MetsuOS
pillow = { version = "^10.0", optional = true, priority = "high" }

[tool.metsudep.groups]
render-backend = { 
  at_least_one = true,
  alternatives = [
    { name = "pygame", version = "^2.5", priority = "high", platform = "linux" },
    { name = "pyglet", version = "^2.0", priority = "medium" },
    { name = "kivy", version = "^2.3", priority = "low", platform = "android" }
  ]
}

[tool.metsudep.host_deps.windows]
pywin32 = "^306"

[tool.metsudep.licenses]
required_layer = "fsf-fan"   # Solo paquetes compatibles GPL-3.0 o superior
```

## Ventajas frente a alternativas existentes

| Característica                         | pip + requirements | Poetry/PDM | Conda | MetsuDepManager |
|--------------------------------------- |--------------------|------------|-------|-----------------|
| Resolución avanzada de conflictos      | ✗                  | ✓          | ✓     | ✓               |
| Marcadores por SO y versión            | limitado           | ✓          | ✓     | ✓ (ampliado)    |
| Dependencias opcionales y extras       | ✗                  | ✓          | ✓     | ✓               |
| Grupos “al menos uno obligatorio”      | ✗                  | ✗          | ✗     | ✓               |
| Comprobación automática de licencias   | ✗                  | ✗          | ✗     | ✓               |
| Priorización dinámica de paquetes      | ✗                  | ✗          | ✗     | ✓               |
| Integración nativa con mosLib          | ✗                  | ✗          | ✗     | ✓               |

## Referencias bibliográficas que apoyan esta propuesta

1. [Poetry – Documentación oficial 🟡③🌐](https://python-poetry.org/docs/) - La base técnica más sólida para gestores modernos de dependencias en Python (actualizada continuamente).
2. [Learning Python, 5ª edición – Mark Lutz 🟡③🌐](https://www.oreilly.com/library/view/learning-python-5th/9781449355722/) - Capítulo 23 sobre empaquetado y distribución; referencia clásica aún vigente.
3. [The Hitchhiker’s Guide to Python – Packaging 🟡③🌐](https://docs.python-guide.org/writing/structure/#packaging) - Guía práctica mantenida por la comunidad sobre mejores prácticas de empaquetado.
4. [PEP 508 – Dependency specification for Python 🟡③🌐](https://peps.python.org/pep-0508/) - Especificación oficial de marcadores y requisitos de dependencias.
5. [PEP 621 – Storing project metadata in pyproject.toml 🟡③🌐](https://peps.python.org/pep-0621/) - Estándar moderno para metadatos de proyecto y dependencias.
6. [REUSE – Free Software Foundation Europe 🟡③🌐](https://reuse.software/) - Herramienta y guía oficial para cumplimiento automático de licencias en proyectos de software.

## Referencias que refutan o matizan la necesidad de un gestor propio

1. [PDM – Gestión de dependencias y grupos 🟡③🌐](https://pdm-project.org/latest/usage/dependency/) - Documentación oficial de PDM que detalla el uso de grupos opcionales (extras), marcadores condicionales y hooks para una resolución flexible, argumentando por qué esto suele bastar sin solvers custom.
2. [Conda – Managing environments 🟡③🌐](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) - Documentación oficial de Conda defendiendo su capacidad multi-plataforma y gestión de licencias vía canales curados.
3. [Python Packaging User Guide – Best practices 🟡③🌐](https://packaging.python.org/guides/) - Guía oficial que desaconseja sobre-ingeniería en empaquetado y recomienda herramientas estándar.
4. [Python in a Nutshell, 4ª edición – Alex Martelli et al. 🟡③🌐](https://www.oreilly.com/library/view/python-in-a/9781098113544/) - Capítulo de empaquetado que advierte explícitamente contra reinventar la rueda.
5. [PyCon US 2023 – “Modern Python Packaging: Avoiding Common Pitfalls” – Itamar Turner-Trauring 🟡③🌐](https://www.youtube.com/watch?v=3Z1W4qW7L0M) - Charla en inglés con subtítulos (2023) que muestra pitfalls en packaging, incluyendo por qué solvers custom pueden ser un lastre, promoviendo herramientas estándar como Poetry para simplicidad.

### Conclusión equilibrada
Aunque es técnicamente posible (y en el caso de MetsuOS justificable) crear un gestor propio como **MetsuDepManager**, la literatura actual y la experiencia de la comunidad Python recomiendan agotar primero todas las posibilidades de Poetry + plugins + hooks antes de embarcarse en una solución 100 % propia. En el caso concreto de MetsuOS, la combinación de requisitos éticos-legales estrictos y la integración profunda con `mosLib` hacen que la solución personalizada sea razonable y, probablemente, la más limpia a medio-largo plazo.

![[Plantilla - 1MT#One More Thing]]