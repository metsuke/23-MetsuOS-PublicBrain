---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.097Z
modified: 2024-04-06T23:49:42.206Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Declaración de variables y asignación en Lenguaje C

[[Aprender el Lenguaje C desde Cero]]

La declaración de variables y la asignación son conceptos fundamentales en el lenguaje de programación C. Aquí te proporcionaré una introducción básica:

### Declaración de variables:
En C, antes de que puedas utilizar una variable, debes declararla. La declaración de una variable le dice al compilador qué tipo de datos almacenará y cuál será su nombre. La sintaxis básica para declarar una variable es:

```c
tipo_dato nombre_variable;
```

Donde:
- `tipo_dato`: Es el tipo de datos que la variable almacenará (por ejemplo, int para enteros, float para números decimales, char para caracteres, etc.).
- `nombre_variable`: Es el nombre que le das a la variable.

Por ejemplo:
```c
int edad;
float altura;
char inicial;
```

### Asignación de valores:
Una vez que has declarado una variable, puedes asignarle un valor utilizando el operador de asignación (`=`). La sintaxis básica es:

```c
nombre_variable = valor;
```

Donde:
- `nombre_variable`: Es el nombre de la variable a la que quieres asignar un valor.
- `valor`: Es el valor que quieres asignar a la variable.

Por ejemplo:
```c
edad = 25;
altura = 1.75;
inicial = 'J'; // Nota: En C, los caracteres se escriben entre comillas simples.
```

### Declaración y asignación combinadas:
En C, también puedes declarar una variable y asignarle un valor en la misma línea. Esto se conoce como inicialización. La sintaxis es:

```c
tipo_dato nombre_variable = valor;
```

Por ejemplo:
```c
int edad = 25;
float altura = 1.75;
char inicial = 'J';
```

### Ejemplo completo:
Aquí tienes un ejemplo completo que muestra la declaración y asignación de variables en C:

```c
#include <stdio.h>

int main() {
    int edad = 25;
    float altura = 1.75;
    char inicial = 'J';

    printf("Edad: %d\n", edad);
    printf("Altura: %.2f\n", altura); // %.2f se utiliza para imprimir solo dos decimales.
    printf("Inicial: %c\n", inicial);

    return 0;
}
```

Este programa imprimirá:

```
Edad: 25
Altura: 1.75
Inicial: J
```

Así es como se realizan las declaraciones de variables y asignaciones en el lenguaje de programación C. Es importante entender estos conceptos básicos para poder escribir programas efectivos en C.