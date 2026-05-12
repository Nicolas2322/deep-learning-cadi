# Semana 13 – Actividad 13: Implementación de un Autoencoder Denoising usando el dataset MNIST en Google Colab

# 1. Introducción

En el campo del Deep Learning, los Autoencoders representan una de las arquitecturas más importantes dentro del aprendizaje no supervisado. Estos modelos tienen como objetivo aprender representaciones compactas de los datos mediante un proceso de compresión y reconstrucción. Su funcionamiento se basa en dos componentes principales: un encoder, encargado de reducir dimensionalidad y extraer características relevantes, y un decoder, cuya función consiste en reconstruir la información original a partir de la representación comprimida.

Dentro de las múltiples variantes de autoencoders, los Denoising Autoencoders tienen una gran relevancia debido a su capacidad para eliminar ruido presente en imágenes o señales. En lugar de simplemente reconstruir la entrada original, este modelo aprende a restaurar información dañada o alterada artificialmente. Esto permite desarrollar modelos más robustos y con mayor capacidad de generalización.

En esta actividad se implementa un Autoencoder Denoising utilizando el dataset MNIST, compuesto por imágenes de dígitos escritos a mano. El propósito principal consiste en comprender cómo una red neuronal puede aprender patrones visuales relevantes para reconstruir imágenes afectadas por ruido artificial.

El desarrollo incluye la carga y preparación del dataset, la generación de ruido artificial, la implementación completa de la arquitectura encoder-decoder, el entrenamiento del modelo y el análisis visual de los resultados obtenidos. Además, se presentan métricas de desempeño y visualizaciones comparativas entre imágenes originales, imágenes ruidosas e imágenes reconstruidas.

La actividad fue desarrollada en Google Colab utilizando TensorFlow/Keras, siguiendo buenas prácticas de programación, documentación y organización del código.

---

# 2. Objetivos

## Objetivo General

Implementar un modelo Autoencoder Denoising utilizando TensorFlow/Keras para reconstruir imágenes del dataset MNIST afectadas por ruido artificial.

## Objetivos Específicos

- Cargar y preprocesar correctamente el dataset MNIST.
- Aplicar ruido artificial sobre las imágenes originales.
- Diseñar una arquitectura encoder-decoder funcional.
- Entrenar el modelo utilizando imágenes ruidosas como entrada.
- Evaluar la capacidad de reconstrucción del modelo.
- Comparar visualmente imágenes originales, ruidosas y reconstruidas.
- Analizar el comportamiento del modelo y sus posibles aplicaciones reales.

---

# 3. Descripción del Dataset

El dataset MNIST es uno de los conjuntos de datos más utilizados en Deep Learning y Visión por Computador. Contiene imágenes en escala de grises de dígitos escritos a mano.

Características principales del dataset:

- 70,000 imágenes en total.
- 60,000 imágenes para entrenamiento.
- 10,000 imágenes para prueba.
- Resolución de 28x28 píxeles.
- Imágenes en escala de grises.
- 10 clases correspondientes a los dígitos del 0 al 9.

Este dataset resulta adecuado para Autoencoders debido a su simplicidad y tamaño moderado, permitiendo observar claramente el proceso de reconstrucción de imágenes.

---

# 4. Preprocesamiento del Dataset

Antes del entrenamiento del modelo, fue necesario aplicar varias etapas de preprocesamiento con el fin de garantizar que los datos fueran adecuados para el aprendizaje.

Inicialmente, las imágenes fueron normalizadas dividiendo cada píxel entre 255. Esto permite trabajar con valores en el rango [0,1], facilitando la estabilidad numérica durante el entrenamiento.

Posteriormente, las imágenes fueron redimensionadas agregando una dimensión adicional correspondiente al canal de color, requerida por TensorFlow/Keras para trabajar con capas convolucionales.

Finalmente, se añadió ruido gaussiano artificial sobre las imágenes originales. Este ruido tiene como propósito deteriorar parcialmente la información visual para que el modelo aprenda a reconstruir la imagen limpia.

---

# 5. Generación de Ruido Artificial

El proceso de denoising requiere modificar artificialmente las imágenes originales para generar un escenario de reconstrucción.

Se utilizó ruido gaussiano aleatorio mediante una distribución normal. Este ruido fue agregado pixel por pixel sobre las imágenes originales.

Posteriormente, los valores fueron limitados nuevamente al rango [0,1] utilizando la función `clip`, evitando valores inválidos.

El uso de ruido artificial permite simular problemas reales presentes en procesamiento de imágenes, como:

- Imágenes borrosas.
- Interferencias en sensores.
- Compresión con pérdida.
- Ruido electrónico.
- Transmisión de imágenes dañadas.

---

# 6. Arquitectura del Autoencoder

El modelo implementado corresponde a un Autoencoder Convolucional Denoising.

La arquitectura se divide en dos partes principales:

## Encoder

La fase encoder tiene como objetivo extraer características relevantes y reducir progresivamente la dimensionalidad de la imagen.

Se utilizaron:

- Capas Conv2D.
- Funciones de activación ReLU.
- MaxPooling para reducción espacial.

El encoder aprende representaciones comprimidas de los dígitos.

## Decoder

La fase decoder reconstruye la imagen original a partir de la representación comprimida generada por el encoder.

Se utilizaron:

- Capas Conv2D.
- UpSampling2D.
- Función sigmoide en la salida.

La salida final tiene el mismo tamaño de la imagen original: 28x28x1.

---

# 7. Entrenamiento del Modelo

El entrenamiento se realizó utilizando:

- Optimizador Adam.
- Función de pérdida Binary Crossentropy.
- Batch size de 128.
- 20 épocas.

Durante el entrenamiento:

- La entrada corresponde a imágenes con ruido.
- La salida esperada corresponde a imágenes originales sin ruido.

Esto obliga al modelo a aprender representaciones robustas capaces de eliminar el ruido presente en la entrada.

También se utilizó EarlyStopping para evitar sobreajuste y detener el entrenamiento automáticamente cuando la pérdida de validación deja de mejorar.

---

# 8. Resultados del Entrenamiento

Durante el entrenamiento se registraron métricas relacionadas con:

- Training Loss.
- Validation Loss.

Las gráficas obtenidas permiten analizar:

- Velocidad de convergencia.
- Estabilidad del aprendizaje.
- Posibles signos de overfitting.
- Calidad del proceso de reconstrucción.

La reducción progresiva de la pérdida evidencia que el modelo logró aprender patrones importantes de las imágenes.

---

# 9. Evaluación Visual de Resultados

La evaluación principal de un Denoising Autoencoder se realiza visualmente.

Se compararon tres tipos de imágenes:

1. Imagen original.
2. Imagen con ruido.
3. Imagen reconstruida por el modelo.

Los resultados muestran que el modelo logra eliminar gran parte del ruido mientras conserva la estructura principal del dígito.

La calidad de reconstrucción demuestra que el encoder aprendió características relevantes de los datos y que el decoder fue capaz de reconstruir información visual coherente.

---

# 10. Métricas y Análisis del Modelo

El desempeño del modelo fue evaluado utilizando la pérdida de reconstrucción.

Se observó:

- Buena convergencia del modelo.
- Reconstrucción estable de imágenes.
- Reducción significativa del ruido.
- Capacidad adecuada de generalización.

Sin embargo, algunas imágenes con niveles altos de ruido presentan pequeñas deformaciones o pérdida de detalles finos.

Esto es normal debido a las limitaciones de capacidad del modelo y la complejidad del proceso de reconstrucción.

---

# 11. Aplicaciones Reales de los Autoencoders

Los Autoencoders tienen aplicaciones importantes en múltiples áreas:

- Eliminación de ruido en imágenes médicas.
- Restauración de fotografías antiguas.
- Compresión de imágenes.
- Detección de anomalías.
- Generación de representaciones latentes.
- Sistemas de recomendación.
- Seguridad y biometría.

Los Denoising Autoencoders específicamente son ampliamente utilizados en problemas de restauración visual y mejora de calidad de imágenes.

---

# 12. Conclusiones

El desarrollo de esta actividad permitió comprender el funcionamiento interno de un Autoencoder Denoising y su capacidad para reconstruir imágenes deterioradas mediante aprendizaje profundo.

La arquitectura encoder-decoder demostró ser efectiva para aprender representaciones compactas y reconstruir información visual relevante.

La incorporación de ruido artificial permitió evidenciar cómo el modelo aprende patrones robustos y desarrolla capacidad de generalización frente a datos alterados.

Las visualizaciones comparativas mostraron claramente la diferencia entre imágenes originales, imágenes con ruido e imágenes reconstruidas, validando el correcto funcionamiento del modelo.

Finalmente, esta actividad permitió fortalecer conceptos fundamentales relacionados con aprendizaje no supervisado, extracción de características y redes neuronales generativas, constituyendo una base importante para arquitecturas más avanzadas utilizadas actualmente en Inteligencia Artificial.
