# Semana 4 - Optimización de Redes Neuronales

## Objetivo

Comparar el rendimiento de una red neuronal utilizando diferentes técnicas de optimización, específicamente los optimizadores SGD y Adam.

## Metodología

Se implementó una red neuronal con la misma arquitectura en ambos casos, variando únicamente el optimizador utilizado durante el entrenamiento.

## Configuraciones evaluadas

* SGD (Stochastic Gradient Descent)
* Adam (Adaptive Moment Estimation)

## Resultados

El optimizador Adam mostró una convergencia más rápida, reduciendo la función de pérdida en menos épocas. Además, alcanzó una mayor precisión en comparación con SGD.

Por otro lado, SGD presentó un aprendizaje más lento y requirió más iteraciones para obtener resultados similares.

## Conclusión

El optimizador Adam es más eficiente para este tipo de problema, ya que mejora tanto la velocidad de entrenamiento como el rendimiento del modelo.

## Cómo ejecutar

Abrir el notebook en Google Colab y ejecutar todas las celdas para reproducir los resultados.

# Semana 4 - Regularización en Redes Neuronales

## Objetivo

Aplicar técnicas de regularización para reducir el sobreajuste en una red neuronal.

## Metodología

Se comparó un modelo base sin regularización con un modelo que utiliza Dropout.

## Configuración

* Modelo sin regularización
* Modelo con Dropout

## Resultados

El modelo con Dropout reduce el sobreajuste y mejora la generalización.

## Conclusión

La regularización permite obtener modelos más estables y con mejor desempeño en datos no vistos.

## Cómo ejecutar

Abrir el notebook en Google Colab y ejecutar todas las celdas.

