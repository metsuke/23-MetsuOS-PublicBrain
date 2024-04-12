---
iaStatus: 8
iaStatus_Generado: "H"
iaStatus_Supervisado: "-"
iaStatus_Validado: "-"
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.188Z
modified: 2024-04-12T15:04:13.767Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 91
nav_primary: 
nav_secondary: 
tags:
---
# Estructurar una Microagencia de Marketing Digital

[[PublicBrain/Index]] | [[Mis Apuntes del Curso de Platzi Estructurar una Microagencia de Marketing Digital]]

Inspirado en este [[Curso de Platzi sobre Estructurar una Microagencia de Marketing Digital]] estoy desarrollando mi metodología sobre habilidades, perfiles y tareas para MetsuOS tomando como base lo aprendido en este curso, para posteriormente integrar mas conocimientos.

## Organigrama de la microagencia

{[MOS::Modelos::Organizaciones::Negocio::MicroagenciaPublicidad::GetStructure]}

* [[Rol Gestión Empresarial|Gestión ste rol se Empresarial]]
	* [[PublicBrain/Rol Comercial|Comercial]]
	* [[Rol Administración Negocios|Administración]]
	* [[Rol Account Manager|Account Manager]]
		* [[Rol Project Manager|Project Manager]]
			* [[Departamento Marketing (Microagencia Marketing Digital)|Marketing]]
				* [[Rol Experto en Embudos de Venta|Expertos en Embudos de ventas]]
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


## ¡Consigue un mes extra gratis en tu suscripcion a Platzi!

Si te interesan los cursos que recomiendo y quieres suscribirte, hazlo a través de [mi enlace de referidos en Platzi](https://platzi.com/r/metsuke) y conseguirás un mes gratis en tu suscripción (y a la vez me regalarás otro a mi sin coste adicional ¡gracias!).


## Log

* Fase 0: Tomar apuntes del curso... DONE
* Fase 1: Modelar agencia (departamentos, puestos ...) ... IN PROGRESS
* Fase 2: Modelar puestos (rol, responsabilidades ...) .. IN PROGRESS
* Fase 3: Modelar roles, habilidades (duras y blandas) .. IN PROGRESS
* Fase 4: Modelar cada uno de los elementos de responsabilidad, etc, etc, etc) ... FUTURE
* Fase 5: Enlazar esto con la ejecución real de las diferentes tareas via MetsuOS ... FUTURE
* Fase 6: Georgi Dan ... FUTURE


