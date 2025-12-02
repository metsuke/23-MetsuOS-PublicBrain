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
created: 2025-12-01T07:38:01.535Z
modified: 2025-12-01T07:53:35.433Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_003.mp4
---
# Objetivo del Curso - Construir MetsuDepManager, un Gestor de Paquetes Práctico, Ético y Personalizable 🟡③

![Objetivo del Curso - Construir MetsuDepManager, un Gestor de Paquetes Práctico, Ético y Personalizable](PublicBrain/_resources/278da1b50d1680cf6fb27493c9c2e5ba_MD5.jpg)

[[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

Imagina que estás cansado de que herramientas como pip o Poetry te dejen a merced de dependencias dudosas o entornos que no controlas del todo. Ahí entra este curso de Metsuke: no es solo teoría, sino un camino directo para que termines con **MetsuDepManager** en tus manos, un gestor de paquetes Python que usa Poetry como motor pero añade capas de sentido común y protección real. Al final, tendrás algo que funciona de verdad en proyectos serios, especialmente si trabajas en MetsuOS, ese sistema operativo que apuesta por la inclusión a través de videojuegos. Es como pasar de un coche básico a uno con frenos de emergencia y GPS ético: seguro, adaptable y listo para lo que venga.

## ¿Por qué MetsuDepManager destaca en la práctica?

Este gestor no reinventa la rueda; envuelve Poetry de forma lista para usar, aprovechando sus fortalezas (como el Core para resolver dependencias o el Installer para montarlo todo sin dramas). Pero lo que lo hace especial es cómo se adapta a la vida real:
- **Comandos que resuelven problemas reales**: Además de los clásicos como `init` o `add`, incluye `audit` para cazar vulnerabilidades al vuelo, `policy` para aplicar reglas éticas (nada de paquetes con sorpresas ocultas) o `verify-sbom` para chequear el "inventario" de software en formatos estándar como CycloneDX.
- **Ética en cada paso**: Un motor de políticas que vigila todo: filtra licencias raras, bloquea telemetría no deseada y chequea vulnerabilidades con herramientas como Safety u OSV. Es el guardián que asegura que tu código respete principios de desarrollo responsable, ideal para proyectos inclusivos donde la transparencia no es opcional.
- **Configuración a tu medida**: Olvídate de complicaciones; todo se define en un simple `metsudep.toml` o YAML. Puedes firmar excepciones con cripto, simular instalaciones en modo "prueba" o adaptarlo a entornos sin red. Perfecto para cumplir con RGPD o NIS2 sin sudar.

Se basa en PEPs sólidas (como la 517 para builds repetibles o la 621 para metadatos), y el curso te obliga a probarlo todo: tests con pytest al 95%, tipado con mypy y CI en GitHub Actions. Al final, no es solo código; es un hábito de desarrollo limpio.

## Estructura del Curso: De la Idea al Proyecto Listo

El curso te lleva de la mano, módulo a módulo, para que construyas MetsuDepManager sin atascos:
1. **Por qué hacerlo**: Ves las limitaciones de Poetry en mundos reales (regulaciones, educación, seguridad) y por qué un wrapper propio salva el día.
2. **Bajo el capó de Poetry**: Aprendes su API para invocarla de forma segura, con logs y filtros que evitan sorpresas.
3. **Diseño con cabeza**: Armas la arquitectura (CLI con Typer y Rich, plugins fáciles) y configuras el `pyproject.toml` base.
4. **El núcleo en acción**: Implementas el wrapper, integras auditorías y lo preparas para offline o sandbox.
5. **Pulido y pruebas**: Añades SBOM, export a requirements.txt y mocks para tests en entornos aislados.
6. **Al mundo**: Publicas en PyPI, revisas con checklists y piensas en extras como una interfaz web.

Terminas con un proyecto open-source que puedes forkear, auditar y escalar. Es hands-on puro: de cero a un gestor que usas en tu curro o hobby.
## Recursos Clave del Curso (para Meterle Mano)

Estos enlaces son el pan de cada día en el curso; úsalos para profundizar mientras codificas MetsuDepManager:

1. [Documentación oficial de Poetry 🟡③🌐](https://python-poetry.org/docs/) .- Documentación oficial de Poetry, herramienta para gestión de dependencias y empaquetado en Python, cubriendo introducción, instalación (pipx, oficial, manual), configuración, comandos básicos y avanzados para proyectos reproducibles en Python 3.9+.
2. [PEP 517: A Build-System Abstraction for Python 🟡③🌐](https://peps.python.org/pep-0517/) .- PEP 517: Formato independiente de sistemas de build para árboles de fuentes en Python, publicada el 30 de septiembre de 2015, que define hooks y metadatos para builds reproducibles.
3. [PEP 518: Specifying Dependencies for Multiple Targets 🟡③🌐](https://peps.python.org/pep-0518/) .- PEP 518: Especificación de dependencias mínimas para sistemas de build en proyectos Python, creada el 10 de mayo de 2016 y en estado Final, para manejar requires en pyproject.toml.
4. [PEP 621: Project Metadata for Dynamic Access 🟡③🌐](https://peps.python.org/pep-0621/) .- PEP 621: Almacenamiento de metadatos de proyectos en pyproject.toml para acceso dinámico, creada el 22 de junio de 2020 y en estado Final, cubriendo campos como name, version y dependencies.
5. [Safety (pyup.io) 🟡③🌐](https://github.com/pyupio/safety) .- Repositorio de Safety, herramienta CLI para verificar dependencias Python contra vulnerabilidades conocidas en bases como PyPI y Snyk, sugiriendo remediaciones y soportando requirements.txt y lock files.
6. [OSV: Open Source Vulnerabilities 🟡③🌐](https://osv.dev/) .- OSV (Open Source Vulnerabilities), base de datos distribuida de vulnerabilidades OSS en ecosistemas como PyPI, con API para consultas por versión o commit, y herramientas como OSV-Scanner para SBOM y contenedores.
7. [CycloneDX: SBOM Standard 🟡③🌐](https://cyclonedx.org/) .- Sitio oficial de CycloneDX, estándar OWASP para BOM en cadena de suministro de software, incluyendo SBOM, SaaSBOM, VEX y más, para mitigación de riesgos cibernéticos.
8. [SPDX: Software Package Data Exchange 🟡③🌐](https://spdx.dev/) .- Sitio de SPDX, estándar ISO/IEC 5962:2021 para SBOM en software, AI y datos, con perfiles para riesgos de seguridad, licencias y herramientas para generación y validación.
9. [Typer: CLI con Python 🟡③🌐](https://typer.tiangolo.com/) .- Documentación de Typer, biblioteca Python para CLIs basadas en type hints, con autocompletado, validación automática y soporte para subcomandos, ideal para interfaces intuitivas.
10. [Rich: Terminal Formatting 🟡③🌐](https://github.com/Textualize/rich) .- Repositorio de Rich, biblioteca Python para texto enriquecido en terminales, con soporte para colores, tablas, progreso, sintaxis y markdown, compatible con Python 3.8+ en múltiples plataformas.

Si te animas a acompañarnos, sales con un tool que no solo resuelve problemas, sino que te hace mejor dev. ¿Quieres un snippet del motor de políticas o detalles de un módulo? Dime.

## Referencias bibliográficas que apoyan la creación de un gestor propio como MetsuDepManager

1. [CNCF TAG Security (2023). *Software Supply Chain Best Practices v2*. 🟡③🌐](https://tag-security.cncf.io/community/working-groups/supply-chain-security/supply-chain-security-paper-v2/Software_Supply_Chain_Practices_whitepaper_v2.pdf) .- Documento blanco que moderniza prácticas de seguridad en cadenas de suministro, con recomendaciones para auditorías regulares, manejo de datos de auditoría, VEX, verificación criptográfica y actualizaciones de ataques/herramientas, organizado por etapas (código fuente, materiales, builds, artefactos, despliegues) para reducir impactos de ataques, incluyendo referencias a PyPI y gestores de dependencias en Python.
2. [European Commission (2024). *Regulation (EU) 2024/2847 on horizontal cybersecurity requirements for products with digital elements (Cyber Resilience Act)*. 🟡③🌐](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32024R2847) .- Reglamento que establece requisitos horizontales de ciberseguridad para productos con elementos digitales, exigiendo diseño seguro por defecto, manejo de vulnerabilidades, integridad en la cadena de suministro, SBOM machine-readable en documentación técnica, due diligence en componentes de terceros (incluyendo FOSS), actualizaciones automáticas gratuitas y notificación de incidentes en 24h, con soporte para herramientas custom en verificación y certificación.
3. [Endor Labs (2024). *Dependency Management Report*. 🟡③🌐](https://www.endorlabs.com/lp/dependency-management-report) .- Informe que analiza tendencias en gestión de dependencias OSS, destacando que menos del 9.5% de vulnerabilidades son explotables a nivel función, un 27% de organizaciones tienen un footprint significativo de dependencias fantasma (con >56% de vulnerabilidades reportadas en ellas), retrasos medianos de 25 días en publicación de parches y riesgos de breaking changes en actualizaciones (95% en upgrades de versión), justificando análisis de reachability y priorización ética para mitigación.

## Referencias que refutan o matizan la necesidad de un gestor propio

1. [Python Packaging Authority (PyPA) (2023). *Installing packages using pip and virtual environments*. 🟡③🌐](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/) .- Guía oficial de PyPA que detalla la instalación de paquetes con pip en entornos virtuales creados con venv, incluyendo creación/activación de entornos, actualización de pip, instalación de paquetes (versiones, extras, desde fuente o Git), uso de requirements.txt y export con pip freeze, enfatizando aislamiento y gestión de dependencias como enfoque estándar.
2. [Poetry (2024). *Announcing Poetry 1.8.0*. 🟡③🌐](https://python-poetry.org/blog/announcing-poetry-1.8.0/) .- Anuncio de Poetry 1.8.0 con soporte PEP 658 para metadata sin descargar wheels completos, lazy-wheel para requests HTTP parciales, validación de archivos con hashes adicionales en instalación y modo no-paquete para gestión pura de dependencias, mejorando velocidad y seguridad sin mención a mirrors privados o export con PEP 658.
3. [Chainguard (2023). *Introducing Wolfi: The first Linux (un)distro designed for securing the software supply chain*. 🟡③🌐](https://www.chainguard.dev/unchained/introducing-wolfi-the-first-linux-un-distro-designed-for-securing-the-software-supply-chain) .- Introducción a Wolfi, una distribución Linux para contenedores que construye paquetes desde fuente para fixes de vulnerabilidades y minimiza dependencias, con imágenes firmadas, SBOMs en build-time y reconstrucción diaria en lugar de updates, reduciendo superficies de ataque y obviando gestores custom mediante imágenes distroless pre-construidas y auditables.

![[Plantilla - 1MT#One More Thing]]