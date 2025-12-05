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
modified: 2025-12-05T01:06:56.507Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_005.mp4
---
# MetsuDepManager - Visión general del proyecto 🟡③

![MetsuDepManager - Visión general del proyecto](PublicBrain/_resources/bcdb26b402ce1818f324f6b0247f7807_MD5.jpg)

* [[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

**MetsuDepManager - Gestor de dependencias ético, seguro, accesible y listo para producción**
## Introducción

MetsuDepManager es un gestor de dependencias ético, seguro, accesible y listo para producción para Python, diseñado específicamente para entornos regulados como empresas con políticas de seguridad estrictas (banca, defensa, sanidad, administraciones públicas), entornos educativos obligados por normativas como la LOMLOE y el Real Decreto 1112/2018 de accesibilidad, sistemas air-gapped o con conexión restringida (industria, investigación clasificada), y proyectos sujetos a regulaciones como RGPD, NIS2, ENS Alto o Ciberseguridad Nacional. Como wrapper ligero sobre Poetry, que actúa como su motor principal, integra un motor de políticas avanzado que asegura cumplimiento normativo (vulnerabilidades, licencias, orígenes geográficos) sin comprometer la velocidad ni la usabilidad. Su enfoque offline-first y su soporte para SBOM (Software Bill of Materials) lo convierten en una herramienta indispensable para mitigar riesgos en la cadena de suministro de software, alineándose con regulaciones como NIS2, ENS Alto, DORA e ITAR/EAR.

El proyecto culminante del curso sobre desarrollo de un gestor de paquetes Python que use Poetry como backend, MetsuDepManager nace dentro de **MetsuOS**, un sistema operativo modular cuya misión fundacional es **la plena inclusión a través de los videojuegos y la tecnología**. Por eso, la accesibilidad no se negocia jamás: es el fundamento ético y técnico no negociable desde el día cero. En un panorama donde las dependencias open-source representan hasta el 80% del código en aplicaciones modernas, pero introducen riesgos geopolíticos, de licencias y de seguridad, MetsuDepManager prioriza la soberanía tecnológica, la accesibilidad (ARIA-compliant) y la transparencia auditable. Este documento presenta la visión integral del proyecto, su arquitectura, características clave y roadmap, configurado para entornos de alta criticidad.

## ¿Qué es Realmente MetsuDepManager?

MetsuDepManager no es “otro gestor de paquetes más”. Es una **capa segura, ética y altamente configurable** construida sobre Poetry que resuelve problemas complejos (CPS aplicado de forma sistemática a un contexto extremadamente específico) que hoy no cubren ni pip, ni Poetry, ni PDM, ni Hatch en entornos exigentes. Su propósito principal es resolver las carencias de las herramientas actuales en contextos estrictamente regulados.

En resumen: **es la herramienta que te gustaría haber tenido cuando tu jefe de seguridad, el delegado de protección de datos o el auditor te pidió “garantías” de lo que instalas**.

## Motivación

El ecosistema Python depende en gran medida de paquetes open-source, pero la gestión de dependencias tradicionales (pip, Poetry) ignora riesgos críticos:
- **Vulnerabilidades**: Ataques como Log4Shell o SolarWinds destacan la fragilidad de la cadena de suministro.
- **Licencias**: Conflictos con GPL en entornos propietarios o requisitos de disclosure en UE.
- **Orígenes Geográficos**: En 2025, tensiones geopolíticas (e.g., sanciones UE a RU/CN, controles US ITAR/EAR) convierten las patentes y tecnologías en vectores de riesgo. Dependencias de orígenes "prohibidos" pueden violar export controls o NIS2.
- **Cumplimiento Sectorial**: ENS Alto exige protección de supply chain en infraestructuras críticas españolas; DORA obliga a testing de dependencias OSS en finanzas.
- **Accesibilidad y Ética**: Entornos educativos y públicos obligados por LOMLOE y RD 1112/2018; privacidad en RGPD sin telemetría no consentida.

MetsuDepManager resuelve esto con políticas preconfiguradas, SBOM enriquecidos y hooks no-intrusivos, manteniendo la simplicidad de Poetry mientras añade capas de resiliencia. Prioriza valores como la transparencia total, la auditoría automática, el principio de menor privilegio, la protección de la privacidad y –de forma explícita y no negociable– la accesibilidad universal.

## Pilares Éticos y Técnicos No Negociables

| Pilar                       | Qué significa en la práctica                                                                                                                                          |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ética**                   | Ninguna dependencia puede violar licencias prohibidas, enviar telemetría no consentida ni introducir vulnerabilidades conocidas sin firma criptográfica de excepción. Incluye perfiles geo para soberanía tecnológica. |
| **Seguridad**               | Motor de políticas + integración automática con Safety, OSS Index, OSV y generación de SBOM (CycloneDX/SPDX).                                                         |
| **Accesibilidad universal** | Requisito desde el día cero, no un añadido posterior (ver sección completa más abajo).                                                                                |
| **Privacidad**              | Modo 100% offline, bloqueo de cualquier llamada externa no autorizada, caché local con pinning de hash+URL.                                                           |
| **Transparencia**           | Todo el código es open-source, auditado y con logging estructurado (structlog).                                                                                       |
| **Resiliencia Geopolítica** | Metadatos geo-org en dependencias para bloqueos/prioridades; perfiles preestablecidos para compliance NIS2/ITAR.                                                      |

## Características Principales

### 1. **Wrapper Inteligente sobre Poetry**
   - Comandos proxy: `metsudep add <pkg>`, `metsudep install`, `metsudep lock` → Aplica políticas pre-instalación.
   - Comandos clásicos adicionales: `init`, `remove`, `update`, `build`, `publish`.
   - Comandos éticos propios: `audit`, `policy`, `sign-exception`, `verify-sbom`, `enforce`.
   - Offline-first: Resolución y caché local; fallback online solo con consentimiento (no-telemetría).
   - Extensibilidad: Plugins via entry-points para resolvers custom (e.g., mirrors EU).
   - Soporte completo para entornos virtuales (venv, virtualenv, conda, pixi).
   - Exportación instantánea a requirements.txt, conda-environment.yml o pip-compile.

### 2. **Motor de Políticas Multi-Capa**
   - **Vulnerabilidades**: Integración con Safety DB y OSV; alertas reachability-based (solo deps explotables).
   - **Licencias**: Perfiles preestablecidos (`permissive`, `copyleft`, `eu-compliant`, `defense-restricted`).
   - **Orígenes Geográficos (Geo-Org)**: Metadatos de país/región en SBOM; políticas para bloqueos/prioridades basadas en regulaciones.
   - **Perfiles Integrados**: Combinación de licencias + geo para zero-config en sectores específicos.
   - Configuración en `metsudep.toml`: Políticas declarativas, excepciones firmadas.

### 3. **Generación y Verificación de SBOM**
   - Formatos: CycloneDX (con `geoOrigin` custom en "supplier") y SPDX 2.3.
   - Enriquecimiento: Inclusión de hashes, licencias resueltas y orígenes geográficos para compliance NIS2/ENS.
   - Comando: `metsudep sbom generate --format=cyclonedx --include-geo`.

### 4. **CLI Profesional y Accesible**
   - Basada en Typer + Rich: Tablas coloridas, progresión ARIA, internacionalización (es/ca/en).
   - Paleta WCAG AA/AAA y segura para daltonismo; flags `--no-color`, `--color=auto/always/never`.
   - Salida estructurada 100% compatible con NVDA, VoiceOver y Orca; mensajes claros en español neutro.
   - Autocompletado, barras de progreso, árboles de dependencias y tema oscuro/claro.
   - Reportes: `metsudep audit --full` → Tabla unificada de riesgos (vuln/lic/geo).
   - Modo CI/CD: Enforcer que falla builds no-compliant.

### 5. **Resiliencia Geopolítica**
   - **Metadatos Geo-Org**: Resueltos via DB local (SQLite con ~10k paquetes pre-cargados); fallback a APIs públicas (PyPI, ClearlyDefined).
   - **Perfiles Geo Preestablecidos**: Activables en config para cumplimiento inmediato.

| Perfil                  | Bloqueados                  | Preferidos                  | Warn >%              | Uso Típico                          |
|-------------------------|-----------------------------|-----------------------------|----------------------|-------------------------------------|
| `global-permissive`    | —                           | —                           | 80% cualquier país   | Open-source general                 |
| `eu-sovereign`         | —                           | ["EU"]                      | 40% US, 20% CN       | Empresas UE estándar                |
| `eu-sovereign-strict`  | ["CN","RU","IR","KP"]       | ["EU","ES","DE","FR","NL"]  | 25% US               | NIS2, ENS Alto, DORA                |
| `defense-es`           | ["CN","RU","IR","KP","BY"]  | ["ES","EU","US-ally"]       | 10% fuera aliados    | Defensa española (CCN)              |
| `us-itar-ear`          | ["CN","RU","IR","KP","SY","VE"] | ["US","NATO","FiveEyes"] | —                    | Export controls US                  |
| `cn-independent`       | —                           | ["CN","HK","SG"]            | 50% US               | Reducción riesgos CFIUS             |
| `offline-airgap`       | —                           | —                           | —                    | Entornos aislados (SCADA)           |

   - Excepciones: `metsudep sign-geo-exception <pkg> --reason="Auditado"`.
   - Integración: Hooks pre-resolución priorizan mirrors por perfil.

### 6. **Modo Sandbox y Entornos Aislados**
   - Manejo de venv/conda/pixi, pinning hash+URL, caché 100% offline.
   - Modo “enforcer” para CI/CD: bloquea merges si alguna dependencia rompe las políticas.

### 7. **Sistema de Plugins**
   - Entry-points para hooks como `pre_add`, `post_install`.
   - Ejemplos reales para resolvers custom.

### 8. **Ética y Accesibilidad: No es un Extra, es el Fundamento**

**Declaración oficial del proyecto** (está literalmente en el README):

> «Ninguna funcionalidad técnica podrá justificar la exclusión de personas con discapacidad. La accesibilidad no es opcional: es la base misma de la ética que defendemos.»

| Área                       | Implementación real y verificable                                                                                                                                                                                                                       | Norma cumplida                         |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------- |
| CLI                        | • Paleta WCAG AA/AAA y segura para daltonismo • Flags --no-color , --color=auto/always/never • Salida estructurada 100 % compatible con NVDA, VoiceOver y Orca • Mensajes claros en español neutro                                                      | WCAG 2.1 – 1.4.1, 1.4.3, 1.4.11, 4.1.2 |
| Configuración accesible    | Sección oficial en metsudep.toml : [accessibility] disable-run = true (para pausar en lectores de pantalla)                                                                                                                                             | WCAG 2.1 AA                            |
| Documentación              | MkDocs + Material for MkDocs (tema accesible por defecto) • Contraste ≥ 7:1 • Navegación 100 % por teclado • Etiquetas ARIA correctas                                                                                                                   | WCAG 2.1 AA completo                   |
| Internacionalización       | Mensajes con gettext. Idiomas: español neutro, catalán e inglés (objetivos futuros: lenguas cooficiales y otros idiomas, validando traducciones a través de humanos aun cuando se ayuden con IA, como medida extra de seguridad y accesibilidad). | Ley 39/2015 (España)                   |
| Pruebas de accesibilidad   | • Automatizadas con axe-core • Revisión manual periódica con NVDA y VoiceOver • Obligatorias en la checklist final                                                                                                                                      | Parte del estándar “production-ready”  |
| Política de contribuciones | Cualquier PR que degrade la accesibilidad será rechazado automáticamente (regla explícita en CONTRIBUTING.md)                                                                                                                                           | Compromiso público verificable         |

- Cumplimiento RGPD: Consentimiento explícito para online.
- Logs estructurados (JSON) para auditorías; no tracking.

### 9. **Publicación y Binarios Standalone**
   - Opcionales con PyInstaller o Nuitka.
   - Publicación a PyPI, wheel.

## Arquitectura

- **Core**: Python 3.11+; dependencias mínimas (Poetry, Tomlkit, Rich, Safety, Typer).
- **Hooks**: Pre/post en Poetry resolver (GeoResolver, LicenseChecker).
- **DB Local**: SQLite para caché geo/lic/vuln; actualizaciones offline.
- **Plugins**: `metsudep.vuln_checker`, `metsudep.geo_resolver`.
- Diagrama ASCII:

```
[User CLI] --> [Policy Engine] --> [Poetry Wrapper]
                   |                 |
                   v                 v
             [SBOM Generator]   [Geo/Lic Resolver]
                   |                 |
                   +--> [DB Local: Vuln/Lic/Geo] <--> [Online Fallback (opt)]
```

- Testing: Pytest >95% cobertura con Hypothesis (property-based testing); mocks para geo escenarios y accesibilidad.

## Configuración Ejemplo: `metsudep.toml`

```toml
[tool.metsudep]
geo_profile = "eu-sovereign-strict"  # NIS2/ENS compliance
license_profile = "eu-compliant"

[accessibility]
disable-run = true  # Pausa para lectores de pantalla

[policies.vuln]
threshold_high = 0  # Bloquea CVSS >7

[geoblock.exceptions]
"numpy" = { country = "US", reason = "OSS auditado, licencia MIT" }
```

Uso: `metsudep add requests --geo-prefer=EU` → "Instalado (origen EU, compliant 100%)."

## Roadmap Completo del Curso (12 + 1 Módulos)

| Módulo | Título                                      | Horas aproximadas | Qué aprenderás (y harás)                                                                                   | Timeline |
| ------ | ------------------------------------------- | ----------------- | ---------------------------------------------------------------------------------------------------------- |----------|
| **0**  | Introducción y motivación ética             | 1-2 h             | Por qué necesitamos herramientas propias, casos reales, presentación de MetsuOS y accesibilidad como pilar | Q1 2025 |
| **1**  | Cómo funciona Poetry por dentro             | 4-6 h             | Arquitectura completa, poetry-core, solver, locker, API interna                                            | Q1 2025 |
| **2**  | Diseño ético e inclusivo de MetsuDepManager | 3-4 h             | Principios éticos, arquitectura modular, accesibilidad desde el diseño                                     | Q1 2025 |
| **3**  | Preparación del proyecto profesional        | 2-3 h             | Estructura, pyproject.toml, ruff, mypy, pre-commit, CI, documentación accesible                            | Q1 2025 |
| **4**  | Wrapper seguro sobre Poetry                 | 4-5 h             | PoetryBackend, timeouts, dry-run, logging estructurado                                                     | Q2 2025 |
| **5**  | Motor de políticas éticas                   | 5-7 h             | Licencias, telemetría, vulnerabilidades, SBOM automático, excepciones criptográficas                       | Q2 2025 |
| **6**  | CLI profesional y accesible                 | 4-6 h             | Typer + Rich, colores seguros, lectores de pantalla, autocompletado                                        | Q2 2025 |
| **7**  | Modo sandbox y entornos aislados            | 3-5 h             | venv/conda/pixi, pinning hash+URL, caché 100 % offline; + Geo-Policies + Perfiles                          | Q3 2025 |
| **8**  | Sistema de plugins                          | 3-4 h             | Entry-points, hooks, ejemplos reales                                                                       | Q3 2025 |
| **9**  | Integración CI/CD y entornos empresariales  | 3-4 h             | GitHub Actions, exportación, modo enforcer; + SBOM + CI/CD Enforcer                                        | Q4 2025 |
| **10** | Testing serio y accesibilidad               | 4-6 h             | pytest + Hypothesis, pruebas de accesibilidad obligatorias                                                 | Q1 2026 |
| **11** | Publicación y binarios standalone           | 2-3 h             | PyPI, wheel, PyInstaller/Nuitka                                                                            | Q1 2026 |
| **12** | Proyecto final y futuro                     | 3-5 h             | Checklist production-ready, ideas de extensión (UI web, multi-lenguaje); + Plugins/UI Web + Multi-Idioma   | Q1 2026 |

Riesgos: Falsos positivos geo → Mitigados con excepciones. Alineación: ENS Alto (supply chain), NIS2 (terceros).

## Entregable Final

Un repositorio open-source 100% funcional que incluye:
- Código completo y comentado.
- Documentación accesible y multilingüe.
- Configuración de políticas por defecto (`metsudep.toml`).
- Checklist de producción (seguridad + accesibilidad + calidad).
- Guía de contribución ética y accesible.

## Fuentes Bibliográficas

### 1. **Regulaciones UE y Españolas**

1. [NIS2 Directive (EU) 2022/2555: Securing supply chains in critical sectors. 🟡③🌐](https://eur-lex.europa.eu/eli/dir/2022/2555/oj/eng) .- EU Directive establishing a high common level of cybersecurity across the EU, focusing on risk management, incident reporting, and supply chain security for critical sectors.
2. [DORA (EU) 2022/2554: OSS dependencies testing in finance. 🟡③🌐](https://eur-lex.europa.eu/eli/reg/2022/2554/oj/eng) .- Regulation on digital operational resilience for the financial sector, including requirements for ICT risk management, incident reporting, and testing of third-party dependencies like OSS.
3. [ENS Alto (RD 311/2022): Risk management in supply chain for public sector. 🟡③🌐](https://www.boe.es/eli/es/rd/2022/05/03/311/con) .- Royal Decree regulating Spain's National Security Framework (ENS) at high level, detailing risk management measures for supply chains in public sector information systems.
4. [LOMLOE y Real Decreto 1112/2018: Accesibilidad en entornos educativos públicos. 🟡③🌐](https://www.boe.es/buscar/doc.php?id=BOE-A-2020-17264) .- Organic Law modifying the education system (LOMLOE) and Royal Decree on web and mobile app accessibility, ensuring inclusive access in public educational environments.
5. [Ley 39/2015 (España): Internacionalización y accesibilidad administrativa. 🟡③🌐](https://www.boe.es/buscar/act.php?id=BOE-A-2015-10565) .- Law on the common administrative procedure, promoting internationalization through electronic administration and accessibility for citizens' interactions with public bodies.

### 2. **Regulaciones US**

1. [ITAR/EAR: Export controls on software/tech data. 🟡③🌐](https://www.ecfr.gov/current/title-22/chapter-I/subchapter-M/part-120) .- US regulations governing the export of defense articles, services, software, and technical data (ITAR via Dept. of State for military items) and dual-use commodities, software, and technology (EAR via Dept. of Commerce), including licensing requirements, deemed exports to foreign persons, and controls on encryption and information security.

### 3. **SBOM Standards**

1. [CycloneDX 1.4: Geo metadata in supplier fields. 🟡③🌐](https://cyclonedx.org/docs/1.4/json/) .- CycloneDX 1.4 JSON specification for software Bill of Materials (SBOM), detailing components, dependencies, licenses, and metadata; note: no geographic metadata is present in supplier fields.
2. [SPDX 2.3: License/compliance focus. 🟡③🌐](https://spdx.github.io/spdx-spec/v2.3/) .- SPDX 2.3 specification providing a data exchange format for software packages, emphasizing license compliance analysis through identification of versions, licenses, and verification processes.
### 4. **Accesibilidad y Ética**

1. [WCAG 2.1: Guidelines for web content accessibility. 🟡③🌐](https://www.w3.org/TR/WCAG21/) .- Web Content Accessibility Guidelines (WCAG) 2.1, a W3C Recommendation extending WCAG 2.0, providing recommendations for making web content more accessible to people with disabilities, including success criteria at levels A, AA, and AAA.
2. [RGPD (EU) 2016/679: Data protection and privacy. 🟡③🌐](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng) .- Regulation (EU) 2016/679 (General Data Protection Regulation - GDPR) on the protection of natural persons with regard to the processing of personal data and on the free movement of such data, repealing Directive 95/46/EC.

### 5. **Reportes Geopolíticos 2025**

1. [Everstream Analytics 2025 Risk Report: Geo instability top threat. 🟡③🌐](https://www.everstream.ai/special-reports/2025-supply-chain-annual-risk-report/) .- Everstream Analytics' 2025 Annual Risk Report identifies the top five supply chain risks for 2025 with assigned scores: climate change/extreme weather (90%), geopolitical instability (80%), cybercrime (75%), rare metals and minerals shortages (65%), and forced labor crackdowns (60%), emphasizing geopolitical instability as a major threat due to political upheaval, conflicts, and tariff risks impacting sourcing, manufacturing, and logistics.
2. [WEF Global Risks 2025: Supply chain vulnerabilities. 🟡③🌐](https://www.weforum.org/publications/global-risks-report-2025/) .- World Economic Forum's Global Risks Report 2025, based on the Global Risks Perception Survey 2024-2025 from over 900 experts, highlights an increasingly fractured global landscape with top immediate risks including state-based armed conflict (geopolitical), extreme weather events (environmental), and societal polarization, alongside long-term concerns like biodiversity loss and critical infrastructure disruptions, all posing significant vulnerabilities to global supply chains through instability, resource scarcity, and economic fragmentation.

### 6. **Referencias Técnicas que Apoyan el Proyecto**

1. [Real Python – Dependency Management with Python Poetry: Tutorial que valida Poetry como backend robusto para wrappers personalizados, destacando su resolver de dependencias y soporte para pyproject.toml. 🟡③🌐](https://realpython.com/dependency-management-python-poetry/) .- Tutorial on Python Poetry for dependency management, validating it as a robust backend for custom wrappers through automatic virtual environment handling and conflict resolution; highlights its dependency resolver for satisfying constraints and transitive dependencies, and support for pyproject.toml including metadata, version constraints, groups, and extras for reproducible environments.
2. [CycloneDX – Especificación oficial SBOM: Herramienta open-source para generar SBOM en formato CycloneDX desde proyectos Python, confirmando la viabilidad de integración automática para cumplimiento normativo. 🟡③🌐](https://cyclonedx.org/specification/overview/) .- Official CycloneDX SBOM specification, an open-source standard for representing supply chain components, dependencies, and vulnerabilities; supports generating SBOMs from Python projects in JSON, XML, and Protocol Buffers formats, with features like dependency graphs, provenance, and extensibility enabling automatic integration for regulatory compliance through machine-readable schemas and attestation support.

### 7. **Referencias que Matizan o Cuestionan el Enfoque**

1. [Chris Warrick – How to Improve Python Packaging (2023): Crítica constructiva al exceso de herramientas y wrappers. Análisis que critica la proliferación de herramientas como Poetry por no adherirse completamente a estándares PEP, sugiriendo que wrappers éticos añaden complejidad innecesaria al ecosistema. 🟡③🌐](https://chriswarrick.com/blog/2023/01/15/how-to-improve-python-packaging/) .- Constructive critique of excessive Python packaging tools and wrappers, analyzing the proliferation of tools like Poetry for not fully adhering to PEP standards (e.g., using custom metadata instead of PEP 621 and non-standard dependency markers), suggesting that such wrappers add unnecessary complexity to the ecosystem; proposes unifying tools under PyPA for a single comprehensive solution, emphasizing standards like PEP 517 and PEP 582 to simplify workflows and reduce fragmentation.

**Conclusión**: MetsuDepManager no pretende ser la herramienta que todo el mundo use a diario. Pretende ser la herramienta que **sí o sí necesitas** cuando ética, seguridad, cumplimiento normativo y accesibilidad universal no son negociables. Y el curso te lleva de la mano, paso a paso, para que seas capaz de crearla, entenderla y –si quieres– mejorarla o adaptarla a tu propia organización.


![[Plantilla - 1MT#One More Thing]]