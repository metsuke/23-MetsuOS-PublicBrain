---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-08T10:19:38.030Z
modified: 2024-04-08T10:25:25.537Z
ver_major: 0
ver_minor: 1
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# Declaración y definición de funciones en Lenguaje C

[[Aprender el Lenguaje C desde Cero]]

Claro, en C, las funciones se declaran y se definen para modularizar el código y facilitar su reutilización. Aquí te explico cómo se declaran y definen las funciones en C:

### Declaración de Funciones

La declaración de una función especifica su interfaz, incluyendo su nombre, tipo de retorno y los tipos de sus argumentos. Esta declaración se coloca generalmente en la parte superior del archivo de código fuente o en un archivo de encabezado (.h) para que otras partes del programa puedan utilizarla.

```c
// Declaración de la función
int suma(int a, int b);
```

### Definición de Funciones

La definición de una función proporciona el cuerpo de la función, que es el conjunto de instrucciones que se ejecutarán cuando la función sea llamada. Por lo general, la definición de la función se coloca después de la declaración o al final del archivo de código fuente.

```c
// Definición de la función
int suma(int a, int b) {
    return a + b;
}
```

### Llamada a Funciones

Después de declarar o definir una función, puedes llamarla desde cualquier parte del programa para ejecutar su código. La llamada a la función se realiza utilizando su nombre seguido de paréntesis que contienen los argumentos, si los hay.

```c
int resultado = suma(3, 4);
```

En este ejemplo, la función `suma` se llama con los argumentos `3` y `4`, y su valor de retorno se almacena en la variable `resultado`.

### Prototipos de Funciones

Un prototipo de función es una declaración de función que proporciona su firma sin proporcionar su implementación. Esto permite al compilador conocer la interfaz de la función antes de que sea definida.

```c
// Prototipo de la función
int suma(int a, int b);

int main() {
    int resultado = suma(3, 4);
    return 0;
}

// Definición de la función
int suma(int a, int b) {
    return a + b;
}
```

### Conclusión

La declaración y definición de funciones en C permite modularizar el código, lo que facilita su comprensión, mantenimiento y reutilización. Es importante entender cómo declarar funciones y proporcionar sus definiciones para crear programas más estructurados y organizados. Además, los prototipos de funciones son útiles para proporcionar al compilador información sobre la interfaz de la función antes de que sea definida.