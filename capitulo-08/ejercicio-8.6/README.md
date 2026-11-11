# Ejercicio 8.6

## Enunciado

**(a)** ¿Cuántos parámetros tendría una LSTM basada en palabras con un vocabulario de 1000 palabras y un estado oculto de tamaño 1000?

**(b)** ¿Cuántos parámetros tendría si el vocabulario tuviera 10 000 palabras y el estado oculto fuera de tamaño 10 000?

**(c)** Considera un transformer simple basado en caracteres con un único mecanismo de auto-atención para predecir el siguiente carácter. El tamaño de ventana es 100, el embedding es de 1000 y hay 64 caracteres. Hay funciones densas para \(q\), \(k\) y \(v\), y la salida de la atención va directamente a un softmax. ¿Cuántos parámetros hay?

**(d)** Si el transformer del inciso anterior fuera basado en palabras, con un vocabulario de 10 000 palabras, ¿cuántos parámetros habría?

## Respuesta

**(a)** Aproximadamente **9 005 000 parámetros**.

**(b)** Aproximadamente **900 050 000 parámetros**.

**(c)** Aproximadamente **3 131 064 parámetros**.

**(d)** Aproximadamente **23 013 000 parámetros**.

## Desarrollo

**(a)** Para una LSTM con vocabulario \(V=1000\) y estado oculto \(H=1000\), los parámetros internos son:

$$4H(V+H+1)=4(1000)(1000+1000+1)=8\,004\,000$$

La salida necesita:

$$HV+V=(1000)(1000)+1000=1\,001\,000$$

Total:

$$8\,004\,000+1\,001\,000=9\,005\,000$$

---

**(b)** Con \(V=10\,000\) y \(H=10\,000\):

$$4H(V+H+1)=4(10\,000)(20\,001)=800\,040\,000$$

La salida necesita:

$$HV+V=(10\,000)(10\,000)+10\,000=100\,010\,000$$

Total:

$$800\,040\,000+100\,010\,000=900\,050\,000$$

---

**(c)** Para 64 caracteres y embedding de 1000:

Embeddings:

$$64(1000)=64\,000$$

Las funciones densas de \(q\), \(k\) y \(v\):

$$3(1000(1000)+1000)=3\,003\,000$$

La salida softmax:

$$1000(64)+64=64\,064$$

Total:

$$64\,000+3\,003\,000+64\,064=3\,131\,064$$

El tamaño de ventana de 100 no multiplica el número de parámetros porque las mismas funciones se reutilizan en todas las posiciones.

---

**(d)** Con vocabulario de 10 000 palabras y embedding de 1000:

Embeddings:

$$10\,000(1000)=10\,000\,000$$

Funciones de \(q\), \(k\) y \(v\):

$$3\,003\,000$$

Salida softmax:

$$1000(10\,000)+10\,000=10\,010\,000$$

Total:

$$10\,000\,000+3\,003\,000+10\,010\,000=23\,013\,000$$

## Referencias

- Poole, D. L., & Mackworth, A. K. (2023). *Artificial Intelligence: Foundations of Computational Agents* (3rd ed.). Exercise 8.6.
- Poole, D. L., & Mackworth, A. K. (2023). *Artificial Intelligence: Foundations of Computational Agents* (3rd ed.). Example 8.11.
