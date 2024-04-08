# Funciones en Lenguaje C

[[Aprender el Lenguaje C desde Cero]]

¡Por supuesto! Las funciones son bloques de código que realizan una tarea específica y pueden ser llamadas desde otras partes del programa para ejecutar esa tarea. En C, las funciones son una parte fundamental del lenguaje y se utilizan para dividir el código en partes más pequeñas y manejables, lo que facilita la organización y la reutilización del código. Aquí tienes una explicación detallada sobre las funciones en C:

### Declaración de Funciones

En C, una función se declara con la siguiente sintaxis:

```c
tipo_de_retorno nombre_de_la_función(argumentos) {
    // Cuerpo de la función
}
```

- `tipo_de_retorno`: Es el tipo de dato que devuelve la función. Puede ser `void` si la función no devuelve ningún valor.
- `nombre_de_la_función`: Es el nombre de la función que estás definiendo.
- `argumentos`: Son los valores que se pasan a la función para que realice su tarea. Pueden ser opcionales.

### Ejemplo de Declaración de una Función

```c
int suma(int a, int b) {
    int resultado = a + b;
    return resultado;
}
```

En este ejemplo, la función `suma` toma dos argumentos de tipo `int` (`a` y `b`) y devuelve un valor de tipo `int`. La función calcula la suma de `a` y `b` y devuelve el resultado.

### Llamada a Funciones

Para llamar a una función en C, simplemente escribe el nombre de la función seguido de paréntesis que contienen los argumentos (si los hay).

```c
int resultado = suma(5, 3);
```

En este ejemplo, la función `suma` se llama con los argumentos `5` y `3`, y el resultado se asigna a la variable `resultado`.

### Funciones de Tipo `void`

Las funciones de tipo `void` no devuelven ningún valor. Pueden ser usadas para realizar tareas sin necesidad de devolver un resultado.

```c
void saludar() {
    printf("¡Hola, mundo!\n");
}
```

### Prototipos de Funciones

Es posible declarar el prototipo de una función antes de su definición. Esto permite al compilador saber que la función existe antes de que se llame.

```c
int suma(int a, int b); // Prototipo de la función

int main() {
    int resultado = suma(5, 3);
    printf("El resultado es: %d\n", resultado);
    return 0;
}

int suma(int a, int b) { // Definición de la función
    int resultado = a + b;
    return resultado;
}
```

### Pasaje de Parámetros por Valor

En C, los argumentos de una función se pasan por valor, lo que significa que se crea una copia local de los datos en la función. Esto significa que cualquier modificación a los parámetros dentro de la función no afectará a las variables originales en la función de llamada.

```c
void duplicar(int x) {
    x = x * 2;
}

int main() {
    int numero = 5;
    duplicar(numero);
    printf("El doble de 5 es: %d\n", numero); // Imprimirá 5, no 10
    return 0;
}
```

### Conclusión

Las funciones son una parte esencial de la programación en C. Permiten modularizar y organizar el código de manera eficiente, facilitando su comprensión, mantenimiento y reutilización. Es importante comprender cómo declarar, definir y llamar a las funciones, así como también entender los conceptos de pasaje de parámetros y devolución de valores.