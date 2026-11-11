# Ejercicio 8.1

## Enunciado

Proporciona los pesos y la estructura de una red neuronal con una función de activación sigmoide en la salida y una capa oculta con activación ReLU, que pueda representar la función OR exclusivo (XOR) de dos valores booleanos. La función es verdadera cuando las entradas tienen valores de verdad diferentes. Asume que verdadero se representa como 1 y falso como 0.

## Respuesta

Se puede representar XOR usando una red con dos entradas, una capa oculta de dos unidades ReLU y una unidad de salida sigmoide.

Las unidades ocultas son:

\[
h_1=relu(x-y)
\]

\[
h_2=relu(-x+y)
\]

y la salida es:

\[
salida=sigmoid(-5+10h_1+10h_2)
\]

Por lo tanto, los pesos de la primera unidad oculta son \(w_x=1\), \(w_y=-1\) y sesgo \(0\); los de la segunda son \(w_x=-1\), \(w_y=1\) y sesgo \(0\). Para la salida, los pesos son \(10\) para \(h_1\) y \(10\) para \(h_2\), con sesgo \(-5\).

## Desarrollo

La función XOR vale 1 únicamente cuando las dos entradas son diferentes:

| x | y | XOR |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

XOR puede escribirse como:

\[
(x\land \neg y)\lor(\neg x\land y)
\]

Por eso se utilizan dos unidades en la capa oculta.

La primera unidad es:

\[
h_1=relu(x-y)
\]

Esta unidad vale 1 únicamente cuando \(x=1\) y \(y=0\):

| x | y | \(x-y\) | \(h_1\) |
|---|---|---:|---:|
| 0 | 0 | 0 | 0 |
| 0 | 1 | -1 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 0 |

La segunda unidad es:

\[
h_2=relu(-x+y)
\]

Esta unidad vale 1 únicamente cuando \(x=0\) y \(y=1\):

| x | y | \(-x+y\) | \(h_2\) |
|---|---|---:|---:|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | -1 | 0 |
| 1 | 1 | 0 | 0 |

Entonces \(h_1\) y \(h_2\) representan los dos casos en los que XOR debe ser verdadero.

Para combinar ambas unidades se utiliza la misma idea del Ejemplo 8.1 para representar un OR mediante una salida sigmoide:

\[
salida=sigmoid(-5+10h_1+10h_2)
\]

Si \(h_1=h_2=0\):

\[
sigmoid(-5)\approx0
\]

Si una de las dos unidades vale 1:

\[
sigmoid(-5+10)=sigmoid(5)\approx1
\]

Por lo tanto:

| x | y | \(h_1\) | \(h_2\) | Entrada a la sigmoide | Salida |
|---|---|---:|---:|---:|---:|
| 0 | 0 | 0 | 0 | -5 | \(\approx0\) |
| 0 | 1 | 0 | 1 | 5 | \(\approx1\) |
| 1 | 0 | 1 | 0 | 5 | \(\approx1\) |
| 1 | 1 | 0 | 0 | -5 | \(\approx0\) |

Así, la red representa correctamente la función XOR.

## Referencias

- Poole, D. L., & Mackworth, A. K. (2023). *Artificial Intelligence: Foundations of Computational Agents* (3rd ed.). Exercise 8.1.
- Poole, D. L., & Mackworth, A. K. (2023). *Artificial Intelligence: Foundations of Computational Agents* (3rd ed.). Exercise 7.9.
- Poole, D. L., & Mackworth, A. K. (2023). *Artificial Intelligence: Foundations of Computational Agents* (3rd ed.). Example 8.1.
