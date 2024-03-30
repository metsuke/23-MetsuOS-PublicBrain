---
iaStatus: 1
iaStatus_Generado: "H"
iaStatus_Supervisado: "-"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-01-25T19:25:05.642Z
modified: 2024-03-30T00:50:17.601Z
ver_major: 0
ver_minor: 2
ver_rev: 42
nav_primary: 
nav_secondary: 
tags:
---
# Estructurar una Microagencia de Marketing Digital

[[PublicBrain/Index]] | [[Mis Apuntes del Curso de Platzi Estructurar una Microagencia de Marketing Digital]]

Inspirado en este [[Curso de Platzi sobre Estructurar una Microagencia de Marketing Digital ]] estoy desarrollando mi metodología sobre habilidades, perfiles y tareas para MetsuOS tomando como base lo aprendido en este curso, para posteriormente integrar mas conocimientos.

## Organigrama de la microagencia

{[MOS::Modelos::Organizaciones::Negocio::MicroagenciaPublicidad::GetStructure]}

* Gestión Empresarial
	* [[PublicBrain/Rol Comercial|Comercial]]
	* Administración
	* Account Manager
		* Project Manager
			* Marketing
				* Expertos en Embudos de ventas
				* Expertos en e-mail marketing
				* Expertos en PPC
				* Expertos en SEO
			* Creativos
				* Diseño Gráfico
				* Redacción publicitaria
				* Desarrollo web

```mermaid
graph TD
    GestionEmpresarial[Gestión Empresarial]
	Administracion[Administración]
	AccountManager[Account Manager]
	Comercial[Comercial]
	ProjectManager[Project Manager]
	ExpertoEmbudoVenta[Embudos Ventas]
	ExpertoEmailMarketing[E-Mail Mktg]
	ExpertoPPC[PPC]
	ExpertoSEO[SEO]
	DiseñoGrafico[Diseño]
	RedacciónPublicitaria[Redacción]
	DesarrolloWeb[Desarrollo]
	PerfilesMktg[Marketing]
	PerfilesCreativos[Creativos]
    GestionEmpresarial --> Administracion
    GestionEmpresarial --> Comercial
    GestionEmpresarial --> AccountManager
    AccountManager --> ProjectManager
    ProjectManager --> PerfilesMktg
    ProjectManager --> PerfilesCreativos
    PerfilesMktg --> ExpertoEmbudoVenta
    PerfilesMktg --> ExpertoEmailMarketing
    PerfilesMktg --> ExpertoPPC
    PerfilesMktg --> ExpertoSEO
    PerfilesCreativos --> DiseñoGrafico
    PerfilesCreativos --> RedacciónPublicitaria
    PerfilesCreativos --> DesarrolloWeb
```

* Fase 0: Tomar apuntes del curso... DONE
* Fase 1: Modelar agencia (departamentos, puestos ...) ... IN PROGRESS
* Fase 2: Modelar puestos (rol, responsabilidades ...) .. IN PROGRESS
* Fase 3: Modelar roles, habilidades (duras y blandas) .. IN PROGRESS
* Fase 4: Modelar cada uno de los elementos de responsabilidad, etc, etc, etc) ... FUTURE
* Fase 5: Enlazar esto con la ejecución real de las diferentes tareas via MetsuOS ... FUTURE
* Fase 6: Georgi Dan ... FUTURE


