---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-05T06:05:40.502Z
modified: 2024-04-05T06:06:10.690Z
ver_major: 0
ver_minor: 1
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# Operadores aritméticos, lógicos y de asignación en Lenguaje C

[[Aprender el Lenguaje C desde Cero]]

¡Por supuesto! Aquí tienes una explicación sobre los operadores aritméticos, lógicos y de asignación en el contexto de aprender el lenguaje C desde cero:

### Operadores Aritméticos
Los operadores aritméticos en C se utilizan para realizar operaciones matemáticas en variables numéricas. Los principales operadores aritméticos son:

- `+` (suma): Se utiliza para sumar dos valores.
- `-` (resta): Se utiliza para restar un valor de otro.
- `*` (multiplicación): Se utiliza para multiplicar dos valores.
- `/` (división): Se utiliza para dividir un valor por otro.
- `%` (módulo): Devuelve el resto de la división entera de un valor por otro.

Ejemplo:
```c
int a = 10, b = 5;
int suma = a + b;       // suma = 15
int resta = a - b;      // resta = 5
int multiplicacion = a * b; // multiplicacion = 50
int division = a / b;   // division = 2
int modulo = a % b;     // modulo = 0
```

### Operadores Lógicos
Los operadores lógicos en C se utilizan para realizar operaciones booleanas. Los principales operadores lógicos son:

- `&&` (AND lógico): Devuelve `true` si ambas condiciones son verdaderas.
- `||` (OR lógico): Devuelve `true` si al menos una de las condiciones es verdadera.
- `!` (NOT lógico): Devuelve `true` si la condición es falsa y viceversa.

Ejemplo:
```c
int x = 5, y = 10;
if (x > 0 && y > 0) {
    // Esta condición se cumple si x y y son mayores que 0
}

int a = 10, b = 5;
if (a == 10 || b == 5) {
    // Esta condición se cumple si a es igual a 10 o b es igual a 5
}

int c = 5;
if (!(c > 10)) {
    // Esta condición se cumple si c no es mayor que 10
}
```

### Operadores de Asignación
Los operadores de asignación se utilizan para asignar valores a variables. El operador de asignación básico es "=". Además, hay operadores compuestos de asignación que realizan una operación y luego asignan el resultado a una variable. Algunos de estos operadores son:

- `+=`: Suma el valor de la derecha al valor de la izquierda y asigna el resultado.
- `-=`: Resta el valor de la derecha al valor de la izquierda y asigna el resultado.
- `*=`: Multiplica el valor de la derecha por el valor de la izquierda y asigna el resultado.
- `/=`: Divide el valor de la izquierda por el valor de la derecha y asigna el resultado.

Ejemplo:
```c
int x = 5;
x += 3; // Ahora x es 8 (5 + 3)
x -= 2; // Ahora x es 6 (8 - 2)
x *= 2; // Ahora x es 12 (6 * 2)
x /= 4; // Ahora x es 3 (12 / 4)
```

Estos son los conceptos básicos de los operadores aritméticos, lógicos y de asignación en el lenguaje C. Dominar estos operadores es fundamental para escribir programas eficientes y funcionales en C.