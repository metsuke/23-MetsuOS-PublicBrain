---
iaStatus: 8
iaStatus_Generado: H
iaStatus_Supervisado: H
iaStatus_Validado: "-"
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.188Z
modified: 2024-05-13T19:38:36.272Z
supervisado: 2024-04-14T14:29:03.798Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 114
nav_primary: 
nav_secondary: 
tags:
---
# Estructurar una Microagencia de Marketing Digital  ⚫①

* [[PublicBrain/Index|Index]] 
	* [[Mis Apuntes del Curso de Platzi Estructurar una Microagencia de Marketing Digital  ⚫①]]
	* [[Glosario de Marketing Digital ⚫①]]

Inspirado en este [[Curso de Platzi sobre Estructurar una Microagencia de Marketing Digital ⚫①]] estoy desarrollando mi metodología sobre habilidades, perfiles y tareas para MetsuOS tomando como base lo aprendido en este curso, para posteriormente integrar mas conocimientos.

## Organigrama de la microagencia

{[MOS::Modelos:
	:Organizaciones::Negocio:
		:MicroagenciaPublicidad::GetStructure]}

* [[Rol Gestión Empresarial|Gestión Empresarial]]
	* [[PublicBrain/Rol Comercial|Comercial]]
	* [[Rol Administración Negocios|Administración]]
	* [[Rol Account Manager|Account Manager]]
		* [[Rol Project Manager|Project Manager]]
			* [[Departamento Marketing (Microagencia Marketing Digital)|Marketing]]
				* [[Rol Experto en Embudos de Venta|Expertos en Embudos de ventas]]
				* [[Rol Experto en EMail Marketing|Expertos en Email marketing]]
				* [[Rol Expertos en PPC|Rol Expertos en PPC]]
				* [[Rol Expertos en SEO|Expertos en SEO]]
			* [[Departamento Creativo (Microagencia Marketing Digital)  ⚫①|Creativo]]
				* [[Rol Diseño Gráfico|Diseño Gráfico]]
				* [[Rol Redacción publicitaria|Redacción publicitaria]]
				* [[Rol Desarrollo web  ⚫①|Desarrollo Web]]

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


![[Platzi_Referal#¡Consigue un mes extra gratis en tu suscripcion a Platzi!]]

## Log

* Fase 0: Tomar apuntes del curso... DONE
* Fase 1: Modelar agencia (departamentos, puestos ...) ... IN PROGRESS
* Fase 2: Modelar puestos (rol, responsabilidades ...) .. IN PROGRESS
* Fase 3: Modelar roles, habilidades (duras y blandas) .. IN PROGRESS
* Fase 4: Modelar cada uno de los elementos de responsabilidad, etc, etc, etc) ... FUTURE
* Fase 5: Enlazar esto con la ejecución real de las diferentes tareas via MetsuOS ... FUTURE
* Fase 6: Georgi Dan ... FUTURE

[[⚫🔴🟡🟢🔵⚪ (🔴②)]] | ①②③④⑤⑥ | ⚫① 🔴② 🟡③ 🟢④ 🔵⑤ ⚪⑥