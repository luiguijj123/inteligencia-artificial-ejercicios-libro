# Ejercicio 8

## Enunciado

Diseña características adecuadas para el aprendizaje por refuerzo en mundos de rejilla estocásticos, como generalizaciones del mundo de 4 × 3, que contengan múltiples obstáculos y múltiples estados terminales con recompensas de +1 o -1.

El objetivo es proponer características que permitan que un agente pueda generalizar su conocimiento en mundos de rejilla más complejos y estocásticos.

## Respuesta

Algunas características adecuadas para representar cada estado serían:

- Distancia al estado terminal positivo más cercano.
- Distancia al estado terminal negativo más cercano.
- Distancia al obstáculo más cercano.
- Cantidad de obstáculos cercanos.
- Dirección hacia el estado terminal positivo más cercano.
- Dirección hacia el estado terminal negativo más cercano.
- Presencia de obstáculos inmediatamente arriba, abajo, izquierda o derecha.
- Posición relativa del agente dentro de la rejilla.

Estas características permiten que el agente describa su situación sin depender únicamente de la posición exacta de cada casilla.

## Desarrollo

Un estado puede representarse mediante un vector de características:

$$\phi(s)=[d_{+}(s),d_{-}(s),d_{obs}(s),o_N,o_S,o_E,o_O]$$

donde:

- $d_{+}(s)$ es la distancia al estado terminal con recompensa +1 más cercano.
- $d_{-}(s)$ es la distancia al estado terminal con recompensa -1 más cercano.
- $d_{obs}(s)$ es la distancia al obstáculo más cercano.
- $o_N,o_S,o_E,o_O$ indican si existe un obstáculo inmediatamente al norte, sur, este u oeste.

Para calcular las distancias puede utilizarse la distancia Manhattan:

$$d((x_1,y_1),(x_2,y_2))=|x_1-x_2|+|y_1-y_2|$$

Si $T_{+}$ representa el conjunto de estados terminales con recompensa +1, entonces:

$$d_{+}(s)=\min_{t\in T_{+}} d(s,t)$$

De forma similar, si $T_{-}$ representa los estados terminales con recompensa -1:

$$d_{-}(s)=\min_{t\in T_{-}} d(s,t)$$

Estas distancias permiten distinguir qué tan cerca se encuentra el agente de una recompensa positiva o de una situación desfavorable.

También puede representarse la presencia de obstáculos con valores binarios. Por ejemplo:

$$o_N=
\begin{cases}
1 & \text{si hay un obstáculo al norte}\\
0 & \text{en otro caso}
\end{cases}$$

y de manera equivalente para $o_S$, $o_E$ y $o_O$.

En un mundo de rejilla más grande, usar únicamente la posición exacta del agente puede dificultar la generalización. En cambio, estas características describen propiedades comunes de muchos estados. Por ejemplo, dos posiciones distintas pueden tener una distancia similar a un terminal positivo y obstáculos en direcciones parecidas.

En un entorno estocástico, donde una acción no siempre lleva al estado esperado, este tipo de representación permite que el agente aprenda qué situaciones son favorables o peligrosas de forma más general, en lugar de memorizar cada casilla de manera independiente.

## Referencias

- Russell, S. J., & Norvig, P. (2021). *Artificial Intelligence: A Modern Approach* (4th ed.). Pearson. Exercise 8.
