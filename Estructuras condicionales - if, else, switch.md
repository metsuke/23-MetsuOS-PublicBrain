# Estructuras condicionales - if, else, switch

¡Por supuesto! Las estructuras condicionales en el lenguaje C son fundamentales para tomar decisiones dentro de un programa. Aquí tienes una explicación de las principales estructuras condicionales: `if`, `else`, `switch`.

### 1. `if-else`

La estructura `if-else` permite ejecutar un bloque de código si una condición es verdadera (`if`), y otro bloque si la condición es falsa (`else`).

```c
if (condición) {
    // Bloque de código si la condición es verdadera
} else {
    // Bloque de código si la condición es falsa
}
```

Ejemplo:

```c
int edad = 20;

if (edad >= 18) {
    printf("Eres mayor de edad\n");
} else {
    printf("Eres menor de edad\n");
}
```

### 2. `switch`

La estructura `switch` se utiliza para tomar decisiones basadas en el valor de una expresión. Permite evaluar múltiples casos y ejecutar bloques de código correspondientes a cada caso.

```c
switch (expresión) {
    case valor1:
        // Bloque de código si la expresión coincide con valor1
        break;
    case valor2:
        // Bloque de código si la expresión coincide con valor2
        break;
    ...
    default:
        // Bloque de código si la expresión no coincide con ningún caso
}
```

Ejemplo:

```c
char operador = '+';
int num1 = 10, num2 = 5;
int resultado;

switch (operador) {
    case '+':
        resultado = num1 + num2;
        break;
    case '-':
        resultado = num1 - num2;
        break;
    case '*':
        resultado = num1 * num2;
        break;
    case '/':
        resultado = num1 / num2;
        break;
    default:
        printf("Operador no válido\n");
}
```

En resumen, las estructuras condicionales `if`, `else` y `switch` son esenciales en C para tomar decisiones y controlar el flujo de ejecución de un programa en función de condiciones específicas.