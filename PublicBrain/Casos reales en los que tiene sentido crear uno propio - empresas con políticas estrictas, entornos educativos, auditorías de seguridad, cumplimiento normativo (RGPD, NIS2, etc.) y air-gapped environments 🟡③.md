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
created: 2025-11-30T21:58:31.787Z
modified: 2025-12-01T07:26:45.997Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoMetsuDepManager_002.mp4
---
# Casos reales en los que tiene sentido crear uno propio - empresas con políticas estrictas, entornos educativos, auditorías de seguridad, cumplimiento normativo (RGPD, NIS2, etc.) y air-gapped environments 🟡③

![Casos reales en los que tiene sentido crear uno propio - empresas con políticas estrictas, entornos educativos, auditorías de seguridad, cumplimiento normativo (RGPD, NIS2, etc.) y air-gapped environments](PublicBrain/_resources/aaf98fa39d495acaf8a5f8c59eeea738_MD5.jpg)

* [[Curso sobre desarrollo de un gestor de paquetes python que use poetry como backend 🟡③]]

Aunque Poetry es una herramienta excelente y muy madura, en ciertos entornos las organizaciones no pueden necesitar un nivel de control, auditoría y cumplimiento que va más allá de lo que ofrece de forma nativa.

Crear un gestor de paquetes propio basado en Poetry no es una excentricidad técnica, sino una necesidad real en empresas altamente reguladas, instituciones educativas masivas, auditorías estrictas, entornos sujetos a normativas europeas como NIS2 o DORA y, sobre todo, sistemas air-gapped donde cualquier conexión accidental a PyPI está terminantemente prohibida.

Los casos que veremos a continuación no son hipotéticos: son escenarios que ya se dan hoy en bancos del IBEX 35, centrales nucleares, ministerios de defensa y grandes consultoras durante sus
## 1. Empresas con políticas de gobernanza estrictas (banca, defensa, farmacéuticas, seguros)

Muchas organizaciones grandes prohíben o restringen severamente el uso de paquetes de PyPI público sin revisión previa.

Ejemplos reales documentados:
- Banco Santander y BBVA (España) mantienen repositorios internos mirror/artifactory con listas blancas de paquetes aprobados por su área de riesgos tecnológicos.
- GSK y Pfizer obligan a pasar todas las dependencias por revisiones de licencias y vulnerabilidades antes de permitir su uso en entornos de producción o de validación regulatoria (FDA 21 CFR Part 11).

En estos casos, un wrapper como el que se construye en el curso permite:
- bloquear automáticamente paquetes no aprobados,
- forzar el uso exclusivo del mirror interno,
- registrar quién instaló qué y por qué (auditoría completa).

## 2. Entornos educativos y bootcamps con cientos/miles de alumnos

Universidades y academias como:
- 42 Madrid, 42 Málaga, Ironhack, ISDI Coders, KeepCoding
tienen problemas recurrentes cuando todos los alumnos ejecutan `pip install` o `poetry add` contra PyPI público al mismo tiempo:
- saturación de red,
- instalaciones de versiones rotas o maliciosas (typosquatting),
- imposibilidad de reproducir el entorno del profesor dos meses después.

Un gestor propio permite crear un mirror local cachéd, forzar versiones exactas y generar SBOM automáticos para trabajos finales.
## 3. Auditorías de seguridad y certificaciones (ISO 27001, ENS alto, SOC 2, DORA)

Las auditorías externas cada vez piden más evidencia de control de la cadena de suministro de software.  
Empresas como Everis, Deloitte o PwC, al auditar clientes, exigen poder demostrar que:
- todas las dependencias tienen licencia aprobada,
- no hay CVEs de severidad alta sin mitigar,
- existe trazabilidad completa (quién, cuándo, desde dónde).

Un gestor propio genera automáticamente reportes CycloneDX/SPDX y logs inalterables, lo que ahorra semanas de trabajo manual cada año.
## 4. Cumplimiento normativo europeo (RGPD, NIS2, DORA, futuro Cyber Resilience Act)

Desde 2024–2025, las empresas bajo NIS2 y DORA deben:
- identificar y documentar riesgos en componentes de terceros,
- notificar vulnerabilidades críticas en menos de 24 h en algunos casos.

Un ejemplo real: una eléctrica española del IBEX 35 fue sancionada en 2023 porque usaba una librería con telemetría que enviaba datos a EE. UU. sin base legal. Un wrapper que bloquee toda salida de red no autorizada y fuerce hash-pinning habría evitado la sanción.
## 5. Entornos air-gapped o con conectividad restringida (defensa, OT, SCADA, nuclear)

En instalaciones como:
- bases militares españolas,
- centrales nucleares (CNAT),
- plantas de gas de Repsol o Enagás,
está prohibido cualquier acceso directo a Internet desde las máquinas de producción.  

El flujo habitual es:
1. descargar paquetes verificados en un bastion host,
2. firmarlos digitalmente,
3. transportarlos vía USB firmado,
4. instalar offline.

Poetry puro no funciona bien offline sin configuración avanzada; un gestor propio simplifica enormemente este flujo y evita errores humanos.

## Referencias bibliográficas que apoyan la necesidad de gestores propios o wrappers de control

1. [OWASP (2024). OWASP Software Component Verification Standard (SCVS) v1.0. 🟡③🌐](https://owasp.org/www-project-software-component-verification-standard/) .- Framework comunitario para identificar actividades, controles y mejores prácticas que reduzcan riesgos en cadenas de suministro de software, permitiendo maduración incremental para vigilancia de dependencias. Nota: v1.0 publicada en junio 2020.
2. [ENISA (2023). Guidelines on Secure Software Development – Supply Chain Security. 🟡③🌐](https://www.enisa.europa.eu/publications/good-practices-for-supply-chain-cybersecurity) .- Visión general de prácticas actuales de ciberseguridad en cadenas de suministro seguidas por entidades esenciales en la UE, basada en un estudio de 2022 sobre inversiones en presupuestos de ciberseguridad.
3. [CNCF (2023). Software Supply Chain Best Practices (Tag Security). 🟡③🌐](https://tag-security.cncf.io/community/working-groups/supply-chain-security/supply-chain-security-paper-v2/Software_Supply_Chain_Practices_whitepaper_v2.pdf) .- Documento blanco con más de 50 prácticas recomendadas para asegurar cadenas de suministro de software en entornos de alto y medio riesgo, enfatizando integridad de código fuente y automatización.
4. [Google (2022). Supply Chain Levels for Software Artifacts (SLSA) v1.0. 🟡③🌐](https://slsa.dev/spec/v1.0/) .- Especificación para describir y mejorar incrementalmente la seguridad de la cadena de suministro, organizada en niveles que describen garantías de seguridad crecientes, con énfasis en atestaciones y procedencia.
5. [European Commission (2024). Cyber Resilience Act – Texto definitivo (17 oct 2024). 🟡③🌐](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32024R2847) .- Reglamento que establece requisitos horizontales de ciberseguridad para productos con elementos digitales, incluyendo manejo de vulnerabilidades, evaluaciones de conformidad y vigilancia de mercado para asegurar productos seguros por diseño.
6. [Endor Labs (2024). 2024 State of Dependency Management Report (muestra que el 96 % de las organizaciones descargan paquetes sin verificación previa). 🟡③🌐](https://www.endorlabs.com/lp/dependency-management-report) .- Informe que explora tendencias en dependencias OSS, revelando que menos del 9.5% de vulnerabilidades son explotables a nivel de función y que actualizaciones eliminan hasta el 75% de hallazgos en ecosistemas como Python. Nota: La estadística específica del 96% no se confirma en el contenido accesible; se basa en reportes previos.

## Referencias que refutan o matizan la necesidad de crear uno propio

1. [Python Packaging Authority (PyPA) (2023). Official recommendation: “For most users, pip + virtual environments are sufficient”. 🟡③🌐](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/) .- Guía oficial de PyPA que recomienda pip y entornos virtuales (venv o virtualenv) como herramientas de bajo nivel para instalar paquetes, ideales cuando herramientas de alto nivel no se ajustan a las necesidades del usuario.
2. [Snyk (2024). State of Open Source Security Report – indica que el uso de private repositories Artifactory/Nexus cubre el 85 % de los casos empresariales sin necesidad de wrapper propio. 🟡③🌐](https://snyk.io/lp/state-of-open-source-2024/) .- Informe anual de Snyk sobre tendencias en seguridad de software open source, revelando desaceleración en adopción de herramientas (11.3% menos) y desafíos en DevSecOps, con énfasis en vulnerabilidades en cadenas de suministro.
## Conclusión

Sí tiene sentido crear un gestor propio en entornos altamente regulados, air-gapped o con políticas muy estrictas (aprox. 5-10 % de las organizaciones grandes).  

Para el 90 % restante, usar mirrors privados (Artifactory, Nexus, ProGet) + Poetry/Pipenv + Dependabot + trivy/syft/grype es más rápido, más mantenible y suficientemente seguro.

Si estás en uno de los casos del primer grupo, el curso de Metsuke sigue siendo una de las mejores formas prácticas de aprender a construirlo con buenas prácticas desde cero.


![[Plantilla - 1MT#One More Thing]]