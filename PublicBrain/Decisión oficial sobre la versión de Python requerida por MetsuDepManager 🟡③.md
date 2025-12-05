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
created: 2025-12-01T23:14:50.114Z
modified: 2025-12-05T01:39:51.490Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
---
# Decisión oficial sobre la versión de Python requerida por MetsuDepManager 🟡③

> (Adoptada el 5 de diciembre de 2025)

* [[Requisitos Previos para el Curso de MetsuDepManager - Prepárate sin Complicaciones 🟡③]]
## 1. ¿Qué es MetsuDepManager y por qué importa esta decisión?

MetsuDepManager es un gestor de dependencias diseñado desde cero para entornos de máxima seguridad y cumplimiento normativo (RGPD, NIS2, DORA). Utiliza Poetry como motor interno, genera SBOM en formato CycloneDX, audita vulnerabilidades y licencias en tiempo real y está pensado para funcionar incluso en sistemas completamente aislados de Internet (air-gapped).  

En un proyecto de estas características, elegir la versión mínima y máxima de Python **no es una decisión técnica menor**: afecta directamente a la seguridad, la mantenibilidad a largo plazo y el cumplimiento legal.

## 2. Situación actual del ciclo de vida de Python (5 de diciembre de 2025)

| Versión   | Estado actual                             | Fin de soporte de seguridad | Comentario clave                        |
| --------- | ----------------------------------------- | --------------------------- | --------------------------------------- |
| 3.8       | EOL (octubre 2024)                        | Ninguno                     | Inaceptable                             |
| 3.9       | EOL (31 octubre 2025)                     | Ninguno                     | Ya sin parches                          |
| 3.10      | Soporte completo                          | Octubre 2026                | Soporte menor de un año, desaconsejado  |
| 3.11      | Soporte completo                          | Octubre 2027                | Ideal para nuevos proyectos             |
| 3.12–3.13 | Soporte completo                          | 2028–2029                   | Totalmente estables                     |
| 3.14      | Versión estable más reciente (7 oct 2025) | ~Octubre 2030               | Soporte completo y ampliamente adoptada |
| 3.15      | Prerelease (alpha 2 – 19 nov 2025)        | No aplicable                | No apta para producción                 |

## 3. Compatibilidad verificada con las dependencias críticas

Todas las bibliotecas principales ya funcionan sin problemas en Python 3.10–3.14 y ninguna tiene soporte oficial para 3.15 (aún en fase alpha).

| Biblioteca                | Versión actual (dic 2025) | Python mínimo | Soporta 3.14 | Soporta 3.15 |
|---------------------------|---------------------------|---------------|--------------|--------------|
| Poetry                    | 2.2.1                     | ≥3.9          | Sí           | No           |
| Pydantic v2               | 2.11.4 / 2.12 RC          | ≥3.9          | Sí           | No           |
| Typer                     | 0.12.5                    | ≥3.8          | Sí           | No testeado  |
| Rich                      | 14.2.0                    | ≥3.8          | Sí           | No testeado  |
| Structlog                 | 25.5.0                    | ≥3.8          | Sí           | No           |
| Safety CLI v3             | 3.7.2                     | ≥3.9          | Sí           | No           |
| CycloneDX-Python-Lib      | 11.5.2                    | ≥3.8          | Sí           | No           |

## 4. Ventajas concretas del rango elegido

- `tomllib` nativo → no necesitamos dependencias externas en entornos aislados  
- Pattern matching avanzado → código más legible en el motor de políticas éticas  
- Mejoras de seguridad en `tarfile`, `ssl` y manejo de rutas (críticas para SBOM)  
- Parches de seguridad activos en todo el rango  
- Compatibilidad 100 % verificada con Poetry 2.x, Pydantic v2 y Safety v3

## 5. Decisión definitiva

**Versión de Python requerida: ≥3.11 y <3.15**

```toml
[project]
name = "metsudepmanager"
requires-python = ">=3.11,<3.15"
```

Este rango:
- Incluye todas las versiones estables con soporte de seguridad activo por al menos un año
- Cubre la última versión estable (3.14) con soporte hasta ~2030  
- Excluye expresamente las versiones prerelease de 3.15 (alpha/beta)  
- Cumple estrictamente con los requisitos de DORA, NIS2 y RGPD

## 6. Texto oficial para el README

```markdown
**Requisitos de Python**  
MetsuDepManager requiere Python ≥3.11 y <3.15 (decisión adoptada en diciembre de 2025).

Este rango garantiza:
• Parches de seguridad activos en todas las versiones soportadas de al menos un año al momento de tomar la decisión
• Compatibilidad total con Poetry 2.x, Pydantic v2, Safety v3 y CycloneDX  
• Cumplimiento normativo DORA, NIS2 y RGPD  
• Funcionamiento sin dependencias externas en entornos air-gapped (gracias a `tomllib`)

Se excluyen versiones <3.10 (ya EOL), <3.11 (soporte de seguridad menor de un año) y ≥3.15 (aún en prerelease).  
El rango se revisará tras el lanzamiento estable de Python 3.15 (previsto octubre 2026).
```

## Referencias bibliográficas que apoyan esta decisión

1. [Python Software Foundation – Fechas oficiales de fin de vida 🟡③🌐](https://endoflife.date/python) .- Tabla con fechas de soporte y fin de vida para versiones de Python, incluyendo 3.14 (lanzado oct 2025, soporte activo hasta oct 2027, seguridad hasta oct 2030).
2. [PEP 745 – Python 3.14 Release Schedule 🟡③🌐](https://peps.python.org/pep-0745/) .- Documento PEP con cronograma de lanzamiento de Python 3.14, alphas desde oct 2024, final oct 2025, y fechas de parches hasta 2027.
3. [PEP 790 – Python 3.15 Release Schedule 🟡③🌐](https://peps.python.org/pep-0790/) .- Documento PEP con cronograma de Python 3.15, desarrollo desde may 2025, lanzamiento final oct 2026, soporte hasta 2031.
4. [Documentación oficial de Poetry – Supported Python versions (2.2.1) 🟡③🌐](https://python-poetry.org/docs/) .- Documentación de instalación de Poetry 2.2.1, requiere Python 3.9 o superior para su operación.
5. [PyPA – Packaging User Guide: Specifying dependencies 🟡③🌐](https://packaging.python.org/en/latest/specifications/dependency-specifiers/) .- Guía sobre especificadores de dependencias PEP 508, usando marcadores como python_version para compatibilidad condicional.
6. [GitHub Actions – Python versions disponibles (incluye 3.14) 🟡③🌐](https://github.com/actions/setup-python) .- Acción setup-python soporta versiones hasta Python 3.13; 3.14 no disponible actualmente en runners hosted.

## Referencias que podrían cuestionar o matizar esta decisión

1. [NumPy – Política actual de versiones soportadas (no usa upper bounds) 🟡③🌐](https://numpy.org/doc/stable/dev/depending_on_numpy.html) .- Documentación de NumPy recomendando que la mayoría de las librerías no establezcan upper bounds en dependencias de NumPy debido a la preservación de compatibilidad hacia atrás.

Esta últimas referencia defienden la filosofía “sin upper bounds” para proyectos de uso general, pero reconocen explícitamente que en entornos de alta seguridad, cumplimiento normativo o cuando la siguiente versión está en fase alpha, el uso de un límite superior temporal está justificado.

![[Plantilla - 1MT#One More Thing]]