---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.477Z
modified: 2024-04-14T14:29:03.757Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 25
nav_primary: []
nav_secondary: []
tags: []
---
# Generar numeros primos en Javascript

[[Algoritmos en Javascript]]

Partiendo de un ejemplo para clase, y tras consultar a ChatGPT llegue a este código junto con la conversación que llevé con la IA para entender el procedimiento. Lo dejo trascrito debido a su interés.

## Charla con ChatGPT

En este desafío te damos como entrada un número positivo mayor a cero y debes regresar un arreglo con todos los números primos menores o iguales a ese número de entrada ordenados de menor a mayor. Recuerda que un número es primo si es solo divisible por 1 y por si mismo. Nota: Todos los números primos son números impares a excepción del número 2. El número 1 no es primo porque no cumple con las dos condiciones mencionadas arriba. Input solution(5); Output [2, 3, 5]

ChatGPT

Claro, aquí tienes una función en JavaScript que toma un número positivo mayor a cero y devuelve un arreglo con todos los números primos menores o iguales a ese número, ordenados de menor a mayor:


```js
function esPrimo(numero) {
  if (numero <= 1) {
    return false;
  }
  if (numero <= 3) {
    return true;
  }
  if (numero % 2 === 0 || numero % 3 === 0) {
    return false;
  }
  let i = 5;
  while (i * i <= numero) {
    if (numero % i === 0 || numero % (i + 2) === 0) {
      return false;
    }
    i += 6;
  }
  return true;
}

function solution(numero) {
  const primos = [];
  for (let i = 2; i <= numero; i++) {
    if (esPrimo(i)) {
      primos.push(i);
    }
  }
  return primos;
}

const numeroEntrada = 5;
const primosEncontrados = solution(numeroEntrada);
console.log(primosEncontrados);

}

const numeroInicial = 15;
const pasosNecesarios = solution(numeroInicial);
console.log(`Para reducir ${numeroInicial} a 1 se necesitan ${pasosNecesarios} pasos.`);
```

En este ejemplo, primero definimos la función `esPrimo` que verifica si un número dado es primo o no utilizando el algoritmo de la criba de Eratóstenes. Luego, la función `solution` utiliza la función `esPrimo` para encontrar y almacenar todos los números primos menores o iguales al número de entrada en un arreglo. Finalmente, se imprime el arreglo de números primos encontrados en la consola.

Metsuke

puedes explicarme como funciona esa funcion esPrimo?

ChatGPT

Por supuesto, estaré encantado de explicarte cómo funciona la función `esPrimo`.

La función `esPrimo` tiene como objetivo determinar si un número dado es primo o no. Utiliza el algoritmo de la criba de Eratóstenes, que es un método eficiente para verificar si un número es primo o no hasta cierto límite.

Aquí hay una explicación paso a paso de cómo funciona la función `esPrimo`:

1. Si el número es menor o igual a 1, no es primo. En este caso, la función devuelve `false`.
    
2. Si el número es 2 o 3, es primo. La función devuelve `true` en este caso.
    
3. Si el número es divisible por 2 o por 3, no es primo. En este caso, la función devuelve `false`.
    
4. La función entra en un bucle que empieza en `i = 5`. Esta elección se basa en el hecho de que todos los números primos mayores que 3 son de la forma `6k ± 1`, donde `k` es un número entero positivo. Entonces, se verifica la divisibilidad del número por `i` y por `i + 2` (que es el siguiente número impar). Si el número es divisible por alguno de estos valores, no es primo y la función devuelve `false`.
    
5. El bucle continúa incrementando `i` en 6 en cada iteración. Esto se debe a que todos los números primos mayores que 3 siguen el patrón de `6k ± 1`.
    
6. Si no se encontró ninguna divisibilidad en el bucle, significa que el número es primo y la función devuelve `true`.
    

En resumen, la función `esPrimo` utiliza el algoritmo de la criba de Eratóstenes para determinar si un número es primo o no. Esto se hace al verificar la divisibilidad del número por varios valores específicos siguiendo patrones matemáticos que son válidos para números primos mayores que 3.

Metsuke

puedes simular la ejecucion paso a paso de la funcion es primo para el numero 5?

ChatGPT

¡Por supuesto! Aquí tienes la simulación paso a paso de cómo se ejecutaría la función `esPrimo` para el número 5:

1. Comenzamos con el número 5.
2. Verificamos si 5 es menor o igual a 1. No lo es, así que continuamos.
3. Verificamos si 5 es igual a 2 o 3. No lo es, así que continuamos.
4. Verificamos si 5 es divisible por 2 o por 3. No es divisible por ninguno de ellos.
5. Iniciamos el bucle con `i = 5`.
    - Verificamos si 5 es divisible por `i` (5). No lo es.
    - Verificamos si 5 es divisible por `i + 2` (7). No lo es.
    - Incrementamos `i` en 6, ahora `i` es 11.
    - Verificamos si 5 es divisible por `i` (11). No lo es.
    - Verificamos si 5 es divisible por `i + 2` (13). No lo es.
    - Incrementamos `i` en 6, ahora `i` es 17.
    - Continuamos este proceso hasta que `i * i` (289) sea mayor que 5.
6. Dado que no se encontró ninguna divisibilidad en el bucle, sabemos que 5 es primo.

En resumen, después de ejecutar la función `esPrimo(5)`, se determina que el número 5 es primo y la función devuelve `true`. Esto concuerda con el hecho de que 5 es un número primo, ya que solo es divisible por 1 y por sí mismo.

Metsuke

puedes explicarme la linea "while (i * i <= numero) {"? no entiendo porque i*i

ChatGPT

Por supuesto, puedo explicarte esa línea en detalle. La línea `while (i * i <= numero) {` es una parte clave del algoritmo utilizado en la función `esPrimo` para verificar si un número es primo o no.

Cuando estamos buscando si un número `n` es divisible por algún otro número, solo necesitamos verificar los divisores hasta la raíz cuadrada de `n`. Esto se debe a que si `n` tiene un divisor mayor que su raíz cuadrada, entonces debe tener otro divisor menor que su raíz cuadrada, lo que contradiría la propiedad de ser un número primo.

La línea `while (i * i <= numero)` implementa esta idea. En cada iteración del bucle, se verifica si `i * i` es menor o igual al número dado. Si este es el caso, entonces `i` es menor o igual a la raíz cuadrada del número, y aún necesitamos continuar buscando divisores. Si `i * i` es mayor que el número, entonces ya hemos superado la raíz cuadrada del número y no necesitamos seguir buscando.

Utilizar `i * i` en lugar de `Math.sqrt(numero)` (la raíz cuadrada) es una optimización. Calcular la raíz cuadrada en cada iteración puede ser costoso computacionalmente, mientras que elevar `i` al cuadrado es más eficiente. Esto es posible debido a la propiedad mencionada anteriormente: si hay un divisor mayor que `i`, debe haber otro divisor menor que `i`.

En resumen, la línea `while (i * i <= numero)` asegura que solo se busquen divisores potenciales hasta la raíz cuadrada del número, lo que mejora la eficiencia del algoritmo para determinar si un número es primo o no.