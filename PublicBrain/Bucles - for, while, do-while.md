---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-08T10:13:38.443Z
modified: 2024-05-15T21:38:39.063Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Bucles - for, while, do-while

[[Aprender el Lenguaje C desde Cero ⚫①]]

Por supuesto, los bucles son una parte fundamental en la programación y son utilizados para ejecutar un bloque de código repetidamente hasta que se cumpla una condición específica. En el lenguaje C, los bucles más comunes son `for`, `while`, y `do-while`. Aquí tienes una explicación de cada uno:

### 1. Bucle `for`

El bucle `for` se utiliza para repetir un bloque de código un número específico de veces. Su estructura general es la siguiente:

```c
for (inicialización; condición; actualización) {
    // Código a repetir
}
```

- La inicialización se ejecuta solo una vez al principio del bucle y se utiliza para inicializar la variable de control del bucle.
- La condición se evalúa antes de cada iteración del bucle. Si es verdadera, se ejecuta el bloque de código del bucle; si es falsa, el bucle se detiene.
- La actualización se ejecuta al final de cada iteración del bucle y se utiliza para modificar la variable de control del bucle.

Ejemplo:

```c
for (int i = 0; i < 5; i++) {
    printf("%d\n", i);
}
```

Este bucle imprimirá los números del 0 al 4.

### 2. Bucle `while`

El bucle `while` se utiliza para repetir un bloque de código mientras una condición específica sea verdadera. Su estructura general es la siguiente:

```c
while (condición) {
    // Código a repetir
}
```

- La condición se evalúa antes de cada iteración del bucle. Si es verdadera, se ejecuta el bloque de código del bucle; si es falsa, el bucle se detiene.

Ejemplo:

```c
int i = 0;
while (i < 5) {
    printf("%d\n", i);
    i++;
}
```

Este bucle también imprimirá los números del 0 al 4.

### 3. Bucle `do-while`

El bucle `do-while` es similar al bucle `while`, pero la condición se evalúa al final de cada iteración. Esto garantiza que el bloque de código se ejecute al menos una vez, incluso si la condición es falsa desde el principio. Su estructura general es la siguiente:

```c
do {
    // Código a repetir
} while (condición);
```

- El bloque de código se ejecuta al menos una vez, y luego la condición se evalúa. Si es verdadera, el bucle se repite; si es falsa, el bucle se detiene.

Ejemplo:

```c
int i = 0;
do {
    printf("%d\n", i);
    i++;
} while (i < 5);
```

Este bucle también imprimirá los números del 0 al 4.

Estos son los tres tipos de bucles más comunes en C y son fundamentales para la construcción de programas que requieran repetición controlada de acciones. Es importante entender cuándo y cómo utilizar cada tipo de bucle según los requisitos específicos de tu programa.