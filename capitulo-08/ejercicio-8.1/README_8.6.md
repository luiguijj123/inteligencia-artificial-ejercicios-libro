# Ejercicio 8.6

## Enunciado

En el Ejemplo 8.11, la LSTM estaba basada en caracteres y tenía aproximadamente 3.5 millones de parámetros.

### (a)

¿Cuántos parámetros tendría una LSTM basada en palabras con un vocabulario de 1000 palabras y un estado oculto de tamaño 1000?

### (b)

¿Cuántos parámetros tendría si el vocabulario tuviera 10 000 palabras y el estado oculto fuera de tamaño 10 000?

### (c)

Considera un transformer simple basado en caracteres con un único mecanismo de atención que realiza auto-atención para predecir el siguiente carácter de un texto. Supón que el tamaño de la ventana es 100, el tamaño del embedding es 1000 y existen 64 caracteres. Como parte del transformer hay funciones densas para \(q\), \(k\) y \(v\) que sirven como entrada al mecanismo de atención, y la salida de la atención va directamente a un softmax. ¿Cuántos parámetros hay?

### (d)

Supón que, en lugar del transformer basado en caracteres del inciso (c), el transformer estuviera basado en palabras, con un vocabulario de 10 000 palabras. ¿Cuántos parámetros habría?

## Respuesta

**(a)** La LSTM tendría aproximadamente **9 005 000 parámetros**.

**(b)** La LSTM tendría aproximadamente **900 050 000 parámetros**.

**(c)** El transformer basado en caracteres tendría aproximadamente **3 131 064 parámetros**.

**(d)** El transformer basado en palabras tendría aproximadamente **23 013 000 parámetros**.

## Desarrollo

### (a) LSTM con vocabulario de 1000 palabras y estado oculto de 1000

Una LSTM utiliza cuatro conjuntos de parámetros para sus diferentes compuertas.

Para cada uno se necesitan pesos desde la entrada, pesos desde el estado oculto anterior y un sesgo.

Si:

$$
V=1000
$$

y

$$
H=1000
$$

los parámetros internos de la LSTM son:

$$
4H(V+H+1)
$$

Sustituyendo:

$$
4(1000)(1000+1000+1)
$$

$$
=4(1000)(2001)
$$

$$
=8\,004\,000
$$

Además, la salida debe convertir el estado oculto en una distribución sobre las 1000 palabras del vocabulario:

$$
HV+V
$$

$$
=(1000)(1000)+1000
$$

$$
=1\,001\,000
$$

Por lo tanto:

$$
8\,004\,000+1\,001\,000
=9\,005\,000
$$

La LSTM tendría aproximadamente:

$$
\boxed{9\,005\,000}
$$

parámetros.

---

### (b) LSTM con vocabulario de 10 000 palabras y estado oculto de 10 000

Ahora:

$$
V=10\,000
$$

$$
H=10\,000
$$

Los parámetros internos de la LSTM son:

$$
4H(V+H+1)
$$

$$
=4(10\,000)(10\,000+10\,000+1)
$$

$$
=4(10\,000)(20\,001)
$$

$$
=800\,040\,000
$$

La capa de salida necesita:

$$
HV+V
$$

$$
=(10\,000)(10\,000)+10\,000
$$

$$
=100\,010\,000
$$

Entonces:

$$
800\,040\,000+100\,010\,000
=900\,050\,000
$$

Por lo tanto, habría aproximadamente:

$$
\boxed{900\,050\,000}
$$

parámetros.

Esto muestra que al aumentar mucho el vocabulario y el tamaño del estado oculto, la cantidad de parámetros aumenta de manera considerable.

---

### (c) Transformer basado en caracteres

El vocabulario tiene 64 caracteres y cada uno se representa con un embedding de tamaño 1000.

Los embeddings necesitan:

$$
64(1000)=64\,000
$$

parámetros.

Las funciones densas para \(q\), \(k\) y \(v\) reciben un vector de tamaño 1000 y producen otro vector de tamaño 1000.

Cada una necesita:

$$
1000(1000)+1000
$$

parámetros, incluyendo el sesgo.

Como existen tres funciones:

$$
3(1000(1000)+1000)
$$

$$
=3(1\,001\,000)
$$

$$
=3\,003\,000
$$

La salida de la atención pasa a un softmax sobre los 64 caracteres:

$$
1000(64)+64
$$

$$
=64\,064
$$

Sumando:

$$
64\,000+3\,003\,000+64\,064
$$

$$
=3\,131\,064
$$

Por lo tanto, el transformer tendría aproximadamente:

$$
\boxed{3\,131\,064}
$$

parámetros.

El tamaño de ventana de 100 indica cuántos caracteres se consideran al mismo tiempo, pero no multiplica el número de parámetros de \(q\), \(k\) y \(v\), ya que las mismas funciones se utilizan para todas las posiciones.

---

### (d) Transformer basado en palabras

Ahora el vocabulario tiene:

$$
V=10\,000
$$

mientras que el tamaño del embedding continúa siendo:

$$
E=1000
$$

Los embeddings necesitan:

$$
10\,000(1000)=10\,000\,000
$$

parámetros.

Las funciones para \(q\), \(k\) y \(v\) siguen necesitando:

$$
3\,003\,000
$$

parámetros.

La salida softmax ahora debe producir una distribución sobre 10 000 palabras:

$$
1000(10\,000)+10\,000
$$

$$
=10\,010\,000
$$

Finalmente:

$$
10\,000\,000+3\,003\,000+10\,010\,000
$$

$$
=23\,013\,000
$$

Por lo tanto, el transformer basado en palabras tendría aproximadamente:

$$
\boxed{23\,013\,000}
$$

parámetros.

## Referencias

- Poole, D. L., & Mackworth, A. K. (2023). *Artificial Intelligence: Foundations of Computational Agents* (3rd ed.). Exercise 8.6.
- Poole, D. L., & Mackworth, A. K. (2023). *Artificial Intelligence: Foundations of Computational Agents* (3rd ed.). Example 8.11.
