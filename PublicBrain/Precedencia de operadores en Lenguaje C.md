---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-07T19:04:22.953Z
modified: 2024-05-15T21:38:39.776Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Precedencia de operadores en Lenguaje C

[[Aprender el Lenguaje C desde Cero ⚫①]]

En lenguaje C, la precedencia de operadores determina el orden en el que las operaciones son evaluadas en una expresión. Es importante entender la precedencia de los operadores para poder escribir expresiones de manera correcta y evitar resultados inesperados.

A continuación se presenta una lista de los operadores en lenguaje C ordenados de mayor a menor precedencia:

1. () [] -> . 	// Paréntesis y operadores de acceso a miembros
2. ! ~ ++ -- - (type)* & sizeof // Operadores unarios
3. * / % 	// Multiplicación, división, módulo
4. + - 	// Suma, resta
5. << >> 	// Desplazamiento de bits
6. < <= > >= 	// Operadores relacionales
7. == != 	// Igualdad y diferente
8. & 	// Operador a nivel de bits AND
9. ^ 	// Operador a nivel de bits XOR
10. | 	// Operador a nivel de bits OR
11. && 	// Operador lógico AND
12. || 	// Operador lógico OR
13. ?: 	// Operador condicional ternario
14. = += -= *= /= %= >>= <<= &= ^= |= 	// Asignación y otros operadores de asignación
15. , 	// Operador de coma

Es importante recordar que los paréntesis pueden usarse para modificar el orden de evaluación de una expresión, ya que los operadores dentro de paréntesis se evalúan antes que los operadores fuera de ellos. Además, en caso de existir operadores con la misma precedencia, se evalúan de izquierda a derecha.

Es recomendable referirse a la tabla de precedencia de operadores en lenguaje C siempre que se esté trabajando con expresiones complejas o se tenga dudas sobre el orden de evaluación de los operadores.
