---
iaStatus: 0
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:30:55.000Z
modified: 2024-03-14T21:53:36.180Z
ver_major: 0
ver_minor: 1
ver_rev: 22
nav_primary: []
nav_secondary: []
tags: []
---
# Entornos Virtuales con Python

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