# Ejercicio 12

## Enunciado

Investiga la aplicación de las ideas del aprendizaje por refuerzo al modelado del comportamiento humano y animal.

Este ejercicio relaciona el aprendizaje por refuerzo con la psicología y la neurociencia, estudiando cómo humanos y animales pueden aprender a partir de recompensas, castigos y experiencias anteriores.

## Respuesta

El aprendizaje por refuerzo puede utilizarse para modelar el comportamiento humano y animal porque ambos pueden modificar sus decisiones según las consecuencias de acciones anteriores. Si una acción produce una recompensa, aumenta la posibilidad de repetirla, mientras que una consecuencia negativa puede reducirla.

Una de las conexiones más importantes entre RL y neurociencia es el error de predicción de recompensa, que representa la diferencia entre la recompensa esperada y la realmente obtenida. Estudios realizados en animales han relacionado este tipo de señal con la actividad de neuronas dopaminérgicas, mientras que estudios en humanos han encontrado señales relacionadas con aprendizaje por recompensa en diferentes regiones del cerebro.

## Desarrollo

En aprendizaje por refuerzo, un agente interactúa con un entorno, realiza acciones y recibe recompensas. A partir de esas experiencias aprende qué acciones producen mejores resultados.

Una forma de representar este aprendizaje es mediante el error de predicción:

$$\delta_t=r_{t+1}+\gamma V(s_{t+1})-V(s_t)$$

donde:

- $r_{t+1}$ es la recompensa recibida.
- $V(s_t)$ es el valor esperado del estado actual.
- $V(s_{t+1})$ es el valor esperado del siguiente estado.
- $\gamma$ indica cuánto se consideran las recompensas futuras.
- $\delta_t$ indica si el resultado fue mejor o peor de lo esperado.

Si la recompensa obtenida es mejor que la esperada, el error de predicción es positivo y el valor asociado a esa situación puede aumentar. Si el resultado es peor de lo esperado, el error es negativo y el valor puede disminuir.

### Comportamiento animal

Schultz, Dayan y Montague estudiaron la actividad de neuronas dopaminérgicas en primates y encontraron un comportamiento relacionado con errores en la predicción de recompensas. Cuando aparecía una recompensa inesperada aumentaba la respuesta; después del aprendizaje, esa respuesta podía desplazarse hacia el estímulo que predecía la recompensa.

Esto presenta una relación con el aprendizaje por refuerzo, ya que el animal no aprende únicamente que existe una recompensa, sino también qué señales permiten predecirla.

Por ejemplo, si un animal aprende que después de una señal determinada recibirá alimento, con la experiencia puede comenzar a asociar la señal con la recompensa futura.

### Comportamiento humano

Las mismas ideas también se han utilizado para estudiar la toma de decisiones humana.

En experimentos de condicionamiento instrumental se ha observado que distintas regiones del estriado participan en procesos relacionados con aprender el valor de las recompensas y seleccionar acciones. Esto se ha relacionado con la idea de *actor-critic* del aprendizaje por refuerzo, donde una parte aprende qué tan bueno es un estado y otra aprende qué acciones conviene realizar.

De esta manera, un modelo de RL puede representar situaciones en las que una persona aprende, mediante prueba y error, qué decisiones producen mejores resultados.

### Aplicaciones al comportamiento

Estas ideas permiten estudiar diferentes comportamientos, por ejemplo:

- Aprendizaje mediante recompensas y castigos.
- Condicionamiento animal.
- Toma de decisiones humanas.
- Formación de hábitos.
- Elección entre recompensas inmediatas y futuras.
- Aprendizaje de acciones mediante prueba y error.

Sin embargo, los modelos de aprendizaje por refuerzo son una simplificación. El comportamiento humano y animal también depende de memoria, emociones, planificación, experiencia previa y otros procesos. Por ello, RL puede modelar algunos mecanismos importantes del aprendizaje y la toma de decisiones, pero no representa por sí solo todo el comportamiento biológico.

## Conclusión

El aprendizaje por refuerzo proporciona una forma matemática de estudiar cómo humanos y animales modifican su comportamiento según las consecuencias de sus acciones. La relación entre el error de predicción de recompensa y señales observadas en sistemas dopaminérgicos muestra una conexión importante entre los modelos computacionales y el aprendizaje biológico. Sin embargo, estos modelos deben considerarse una aproximación, ya que el comportamiento real también depende de otros procesos cognitivos y biológicos.

## Referencias

- Russell, S. J., & Norvig, P. (2021). *Artificial Intelligence: A Modern Approach* (4th ed.). Pearson. Exercise 12.
- Schultz, W., Dayan, P., & Montague, P. R. (1997). A neural substrate of prediction and reward. *Science, 275*(5306), 1593–1599. DOI: 10.1126/science.275.5306.1593.
- O'Doherty, J., Dayan, P., Schultz, J., Deichmann, R., Friston, K., & Dolan, R. J. (2004). Dissociable roles of ventral and dorsal striatum in instrumental conditioning. *Science, 304*(5669), 452–454. DOI: 10.1126/science.1094285.
- Niv, Y. (2009). Reinforcement learning in the brain. *Journal of Mathematical Psychology, 53*(3), 139–154. DOI: 10.1016/j.jmp.2008.12.005.
- Subramanian, A., Chitlangia, S., & Baths, V. (2022). Reinforcement learning and its connections with neuroscience and psychology. *Neural Networks, 145*, 271–287. DOI: 10.1016/j.neunet.2021.10.003.
