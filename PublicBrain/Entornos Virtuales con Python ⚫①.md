---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo
iaStatus_Generado: H
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.176Z
modified: 2024-10-01T21:02:14.354Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 30
nav_primary: 
nav_secondary: 
tags:
---
# Entornos Virtuales con Python ⚫①

[[PublicBrain/Index]]

## ¿Que python y pip se ejecuta?

```sh
which python3
which pip3
```

## Instalar funcionalidad VENV

En caso de Mac no es necesario, si estas en Linux o WSL;

```sh
sudo apt install -y python3-venv
```

## Crear un ambiente para un desarrollo

Desde DENTRO de la carpeta en que queremos que este el ambiente, ejecutamos

```sh
python3 -m venv env
```

## Activar el entorno recien creado

env es el nombre que hemos dado al entorno en la instruccion anterior.

```sh
source env/bin/activate
```

## Desactivar el entorno virtual

```sh
deactivate
```

## Requirements.txt

```sh
pip3 freeze > requirements.txt
```

## Install Deps from Requirements.txt

```sh
pip3 install -r requirements.txt
```

![[Plantilla - 1MT#One More Thing]]