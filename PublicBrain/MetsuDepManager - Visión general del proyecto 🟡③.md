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
created: 2025-12-02T19:08:48.633Z
modified: 2025-12-03T00:20:09.954Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_005.mp4
---
# MetsuDepManager - Visión general del proyecto 🟡③

![MetsuDepManager - Visión general del proyecto](PublicBrain/_resources/bcdb26b402ce1818f324f6b0247f7807_MD5.jpg)

* [[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

**MetsuDepManager - Gestor de dependencias ético, seguro, accesible y listo para producción**

El proyecto culminante del curso es MetsuDepManager, un gestor de dependencias para Python diseñado con un enfoque ético y altamente adaptable. 

Funciona como una capa de envoltura segura sobre Poetry, que actúa como su motor principal. Su propósito principal es resolver las carencias de las herramientas actuales en contextos estrictamente regulados, como empresas con normativas internas rigurosas, entornos educativos, auditorías de ciberseguridad o el cumplimiento de regulaciones europeas como el RGPD o la NIS2. 

Además, se adapta perfectamente a sistemas aislados o sin conexión a internet (air-gapped). En su núcleo, prioriza valores como la transparencia total, la auditoría automática, el principio de menor privilegio, la protección de la privacidad y –de forma explícita y no negociable– la accesibilidad universal.
## 1. ¿Qué es realmente MetsuDepManager?

MetsuDepManager no es “otro gestor de paquetes más”. Es una **capa segura, ética y altamente configurable** construida sobre Poetry que resuelve problemas complejos (CPS aplicado de forma sistemática a un conterxto extremadamente específico) que hoy no cubren ni pip, ni Poetry, ni PDM, ni Hatch en entornos exigentes:

- Empresas con políticas de seguridad estrictas (banca, defensa, sanidad, administraciones públicas).
- Entornos educativos públicos obligados por la LOMLOE y el Real Decreto 1112/2018 de accesibilidad.
- Sistemas air-gapped o con conexión restringida (industria, investigación clasificada).
- Proyectos sujetos a RGPD, NIS2, ENS Alto o Ciberseguridad Nacional.
- Equipos que necesitan auditoría automática, SBOM (Software Bill of Materials) y trazabilidad total.

En resumen: **es la herramienta que te gustaría haber tenido cuando tu jefe de seguridad, el delegado de protección de datos o el auditor te pidió “garantías” de lo que instalas**.

### 2. Pilares Éticos y Técnicos No Negociables

| Pilar                       | Qué significa en la práctica                                                                                                                                          |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ética**                   | Ninguna dependencia puede violar licencias prohibidas, enviar telemetría no consentida ni introducir vulnerabilidades conocidas sin firma criptográfica de excepción. |
| **Seguridad**               | Motor de políticas + integración automática con Safety, OSS Index, OSV y generación de SBOM (CycloneDX/SPDX).                                                         |
| **Accesibilidad universal** | Requisito desde el día cero, no un añadido posterior (ver sección completa más abajo).                                                                                |
| **Privacidad**              | Modo 100% offline, bloqueo de cualquier llamada externa no autorizada, caché local con pinning de hash+URL.                                                           |
| **Transparencia**           | Todo el código es open-source, auditado y con logging estructurado (structlog).                                                                                       |

### 3. Características Técnicas Principales

- Comandos clásicos (`init`, `add`, `remove`, `install`, `update`, `build`, `publish`) + comandos éticos propios: `audit`, `policy`, `sign-exception`, `verify-sbom`, `enforce`.
- CLI profesional construida con **Typer** + **Rich**: tablas, barras de progreso, árboles de dependencias y tema oscuro/claro.
- Sistema de plugins vía entry-points (puedes crear tus propios hooks `pre_add`, `post_install`, etc.).
- Soporte completo para entornos virtuales (venv, virtualenv, conda, pixi).
- Exportación instantánea a `requirements.txt`, `conda-environment.yml` o `pip-compile`.
- Modo “enforcer” para CI/CD: bloquea merges si alguna dependencia rompe las políticas.
- Binarios standalone opcionales con PyInstaller o Nuitka.
- Testing serio: > 95 % cobertura con pytest + Hypothesis (property-based testing).

### 4. Accesibilidad: No es un Extra, es el Fundamento

MetsuDepManager nace dentro de **MetsuOS**, un sistema operativo modular cuya misión fundacional es **la inclusión ética a través de los videojuegos y la tecnología**. Por eso la accesibilidad no se negocia jamás.

| Área                       | Implementación real y verificable                                                                                                                                                                                                                            | Norma cumplida                         |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------- |
| CLI                        | • Paleta WCAG AA/AAA y segura para daltonismo<br>• Flags `--no-color`, `--color=auto/always/never`<br>• Salida estructurada 100 % compatible con NVDA, VoiceOver y Orca<br>• Mensajes claros en español neutro                                               | WCAG 2.1 – 1.4.1, 1.4.3, 1.4.11, 4.1.2 |
| Configuración accesible    | Sección oficial en `metsudep.toml`:<br>```toml:disable-run                                                                                                                                                                                                   |                                        |
| Documentación              | MkDocs + Material for MkDocs (tema accesible por defecto)<br>• Contraste ≥ 7:1<br>• Navegación 100 % por teclado<br>• Etiquetas ARIA correctas                                                                                                               | WCAG 2.1 AA completo                   |
| Internacionalización       | Mensajes con `gettext`<br>Onjetivos a priori: español neutro, catalán e inglés (objetivos futuros leguas cooficiales y otros idiomas validando traducciones a través de humanos aun cuando se ayuden con IA, como medida extra de seguridad y accesibilidad) | Ley 39/2015 (España)                   |
| Pruebas de accesibilidad   | • Automatizadas con axe-core<br>• Revisión manual periódica con NVDA y VoiceOver<br>• Obligatorias en la checklist final                                                                                                                                     | Parte del estándar “production-ready”  |
| Política de contribuciones | Cualquier PR que degrade la accesibilidad será rechazado automáticamente (regla explícita en CONTRIBUTING.md)                                                                                                                                                | Compromiso público verificable         |

**Declaración oficial del proyecto** (está literalmente en el README):
> «Ninguna funcionalidad técnica podrá justificar la exclusión de personas con discapacidad. La accesibilidad no es opcional: es la base misma de la ética que defendemos.»

### 5. Roadmap Completo del Curso (12 + 1 módulos)

| Módulo | Título | Horas aproximadas | Qué aprenderás (y harás) |
|--------|--------|-------------------|--------------------------|
| **0** | Introducción y motivación ética | 1-2 h | Por qué necesitamos herramientas propias, casos reales, presentación de MetsuOS y accesibilidad como pilar |
| **1** | Cómo funciona Poetry por dentro | 4-6 h | Arquitectura completa, poetry-core, solver, locker, API interna |
| **2** | Diseño ético e inclusivo de MetsuDepManager | 3-4 h | Principios éticos, arquitectura modular, accesibilidad desde el diseño |
| **3** | Preparación del proyecto profesional | 2-3 h | Estructura, pyproject.toml, ruff, mypy, pre-commit, CI, documentación accesible |
| **4** | Wrapper seguro sobre Poetry | 4-5 h | PoetryBackend, timeouts, dry-run, logging estructurado |
| **5** | Motor de políticas éticas | 5-7 h | Licencias, telemetría, vulnerabilidades, SBOM automático, excepciones criptográficas |
| **6** | CLI profesional y accesible | 4-6 h | Typer + Rich, colores seguros, lectores de pantalla, autocompletado |
| **7** | Modo sandbox y entornos aislados | 3-5 h | venv/conda/pixi, pinning hash+URL, caché 100 % offline |
| **8** | Sistema de plugins | 3-4 h | Entry-points, hooks, ejemplos reales |
| **9** | Integración CI/CD y entornos empresariales | 3-4 h | GitHub Actions, exportación, modo enforcer |
| **10** | Testing serio y accesibilidad | 4-6 h | pytest + Hypothesis, pruebas de accesibilidad obligatorias |
| **11** | Publicación y binarios standalone | 2-3 h | PyPI, wheel, PyInstaller/Nuitka |
| **12** | Proyecto final y futuro | 3-5 h | Checklist production-ready, ideas de extensión (UI web, multi-lenguaje) |

### 6. Entregable Final

Un repositorio open-source 100 % funcional que incluye:
- Código completo y comentado.
- Documentación accesible y multilingüe.
- Configuración de políticas por defecto (`metsudep.toml`).
- Checklist de producción (seguridad + accesibilidad + calidad).
- Guía de contribución ética y accesible.

### Referencias Bibliográficas que Apoyan el Proyecto

1. [Real Python – Dependency Management with Python Poetry 🟡③🌐](https://realpython.com/dependency-management-python-poetry/) .- Tutorial que valida Poetry como backend robusto para wrappers personalizados, destacando su resolver de dependencias y soporte para pyproject.toml.
2. [CycloneDX – Especificación oficial SBOM 🟡③🌐](https://cyclonedx.org/) .- Herramienta open-source para generar SBOM en formato CycloneDX desde proyectos Python, confirmando la viabilidad de integración automática para cumplimiento normativo.
### Referencias que Matizan o Cuestionan el Enfoque

1. [Chris Warrick – How to Improve Python Packaging (2023) 🟡③🌐](https://chriswarrick.com/blog/2023/01/15/how-to-improve-python-packaging/) – Crítica constructiva al exceso de herramientas y wrappers. .- Análisis que critica la proliferación de herramientas como Poetry por no adherirse completamente a estándares PEP, sugiriendo que wrappers éticos añaden complejidad innecesaria al ecosistema.

**Conclusión**: MetsuDepManager no pretende ser la herramienta que todo el mundo use a diario. Pretende ser la herramienta que **sí o sí necesitas** cuando ética, seguridad, cumplimiento normativo y accesibilidad universal no son negociables. Y el curso te lleva de la mano, paso a paso, para que seas capaz de crearla, entenderla y –si quieres– mejorarla o adaptarla a tu propia organización.


![[Plantilla - 1MT#One More Thing]]