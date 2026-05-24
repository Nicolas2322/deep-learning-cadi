# Semana 14 – Actividad 14: Aplicación de los Conceptos de GANs en Google Colab

## Introducción

Las Redes Generativas Adversarias (GANs, Generative Adversarial Networks) representan una de las arquitecturas más importantes dentro del campo del Deep Learning y la inteligencia artificial generativa. Estas redes fueron propuestas por Ian Goodfellow en 2014 y revolucionaron la manera en que los modelos pueden aprender distribuciones complejas de datos para generar información nueva y sintética.

Una GAN está compuesta por dos redes neuronales principales que trabajan de manera adversarial:

El **Generador (Generator)** tiene como objetivo crear imágenes artificiales que sean lo suficientemente realistas como para engañar al discriminador. Para ello, recibe como entrada un vector de ruido aleatorio y lo transforma progresivamente en una imagen sintética.

El **Discriminador (Discriminator)** funciona como un clasificador binario cuya tarea es diferenciar entre imágenes reales provenientes del dataset e imágenes falsas generadas por el generador.

Durante el entrenamiento, ambas redes compiten constantemente. El generador mejora tratando de producir imágenes más convincentes, mientras que el discriminador mejora aprendiendo a detectar imágenes falsas. Este proceso competitivo permite que el generador aprenda gradualmente patrones complejos presentes en los datos reales.

El objetivo principal de esta actividad es comprender el flujo técnico completo de una GAN, incluyendo la preparación del dataset, construcción del generador y discriminador, entrenamiento adversarial y análisis de resultados obtenidos.

---

# Objetivos de la Actividad

El desarrollo de esta práctica tiene como finalidad aplicar los conceptos fundamentales relacionados con Redes Generativas Adversarias mediante un entorno práctico en Google Colab.

Se busca implementar un modelo GAN funcional capaz de generar imágenes sintéticas utilizando el dataset Fashion MNIST, comprendiendo el funcionamiento interno del proceso adversarial entre generador y discriminador.

Adicionalmente, se pretende analizar cómo evolucionan las imágenes generadas durante el entrenamiento y evaluar las limitaciones del modelo considerando restricciones de hardware, número de épocas y complejidad arquitectónica.

---

# Dataset Utilizado

Para esta actividad se utiliza el dataset **Fashion MNIST**, disponible directamente desde TensorFlow/Keras.

Fashion MNIST es un conjunto de datos compuesto por imágenes en escala de grises de diferentes categorías de prendas de vestir. Este dataset fue desarrollado como reemplazo moderno del clásico MNIST de dígitos escritos a mano.

El dataset contiene:

- 70.000 imágenes en escala de grises.
- Tamaño de imagen de 28x28 píxeles.
- 10 categorías diferentes de ropa.
- División oficial de:
  - 60.000 imágenes para entrenamiento.
  - 10.000 imágenes para prueba.

Las clases incluyen:

- Camisetas
- Pantalones
- Suéteres
- Vestidos
- Abrigos
- Sandalias
- Camisas
- Zapatillas
- Bolsos
- Botas

Este dataset resulta adecuado para GANs debido a su baja complejidad computacional y facilidad para visualizar resultados durante el entrenamiento.

---

# Preprocesamiento del Dataset

Antes del entrenamiento del modelo GAN fue necesario realizar un proceso de preparación y normalización de los datos.

Las imágenes originales poseen valores entre 0 y 255. Para mejorar la estabilidad del entrenamiento, las imágenes fueron normalizadas al rango [-1, 1], ya que la capa de salida del generador utiliza la función de activación `tanh`.

También fue necesario redimensionar el dataset para agregar el canal correspondiente a imágenes en escala de grises.

El flujo de preprocesamiento incluyó:

1. Carga del dataset Fashion MNIST.
2. Conversión de tipo de dato a float32.
3. Normalización de píxeles.
4. Adición del canal de profundidad.
5. Creación de batches utilizando TensorFlow Dataset.

Este procedimiento permite optimizar el flujo de entrenamiento y mejorar el rendimiento computacional.

---

# Arquitectura del Generador

El generador es una red neuronal encargada de transformar ruido aleatorio en imágenes sintéticas.

La arquitectura implementada utiliza capas densas y convolucionales transpuestas para incrementar progresivamente la dimensionalidad espacial de los datos.

La red recibe un vector aleatorio de dimensión 100 y genera imágenes de tamaño 28x28x1.

La arquitectura incluye:

- Capas Dense.
- Batch Normalization.
- LeakyReLU.
- Reshape.
- Conv2DTranspose.

La función de activación final utilizada es `tanh`, lo que permite generar imágenes con valores compatibles con el rango normalizado del dataset.

---

# Arquitectura del Discriminador

El discriminador es una red convolucional cuya función consiste en clasificar imágenes reales y falsas.

La arquitectura implementada utiliza:

- Capas convolucionales Conv2D.
- Funciones LeakyReLU.
- Dropout para regularización.
- Flatten.
- Capa Dense final.

La salida del discriminador corresponde a una probabilidad binaria indicando si la imagen pertenece al dataset real o fue generada artificialmente.

El discriminador aprende continuamente a detectar patrones inconsistentes en las imágenes sintéticas generadas por el modelo adversario.

---

# Entrenamiento Adversarial

El entrenamiento de una GAN difiere significativamente del entrenamiento tradicional de redes neuronales.

Durante cada iteración ocurren dos procesos independientes:

## Entrenamiento del Discriminador

El discriminador recibe:

- Imágenes reales etiquetadas como 1.
- Imágenes falsas etiquetadas como 0.

Su objetivo es maximizar la capacidad de distinguir correctamente ambas categorías.

## Entrenamiento del Generador

El generador produce imágenes falsas utilizando ruido aleatorio.

Posteriormente, estas imágenes son enviadas al discriminador, pero el objetivo ahora es engañarlo para que clasifique las imágenes falsas como reales.

En este proceso:

- El discriminador permanece congelado.
- Solo se actualizan los pesos del generador.

Este entrenamiento competitivo permite que ambas redes mejoren progresivamente.

---

# Métricas y Evaluación

Las GANs no utilizan métricas tradicionales como accuracy global de clasificación multiclase.

En esta actividad se monitorean principalmente:

- Loss del discriminador.
- Loss del generador.
- Evolución visual de imágenes generadas.

La evaluación visual resulta fundamental debido a que el objetivo principal es observar la capacidad del generador para producir imágenes cada vez más realistas.

Durante el entrenamiento se generan imágenes de ejemplo en diferentes épocas para analizar la evolución del aprendizaje.

---

# Resultados Obtenidos

Los resultados muestran cómo el generador mejora progresivamente la calidad visual de las imágenes creadas.

En las primeras épocas, las imágenes generadas contienen ruido aleatorio y formas poco definidas. Sin embargo, conforme avanza el entrenamiento, el modelo comienza a capturar patrones estructurales presentes en el dataset Fashion MNIST.

El discriminador inicialmente domina el entrenamiento debido a su facilidad para detectar imágenes falsas. Posteriormente, el generador mejora y comienza a producir imágenes más convincentes.

Se observa que:

- Las prendas generadas adquieren formas reconocibles.
- La calidad mejora progresivamente.
- El entrenamiento adversarial logra estabilidad parcial.

---

# Dificultades Encontradas

Durante el entrenamiento de GANs pueden aparecer múltiples problemas:

## Inestabilidad del entrenamiento

Las GANs son altamente sensibles a hiperparámetros como learning rate, batch size y arquitectura.

## Dominancia del discriminador

Si el discriminador aprende demasiado rápido, el generador deja de recibir gradientes útiles.

## Mode Collapse

El generador puede producir imágenes muy similares entre sí, reduciendo diversidad.

## Limitaciones computacionales

El entrenamiento prolongado requiere recursos considerables de GPU y tiempo de ejecución.

---

# Aplicaciones Reales de las GANs

Las Redes Generativas Adversarias poseen aplicaciones ampliamente utilizadas en inteligencia artificial moderna:

- Generación de imágenes realistas.
- Restauración y super resolución de imágenes.
- Creación de rostros sintéticos.
- Generación de arte digital.
- Data augmentation.
- Conversión de estilos.
- Deepfakes.
- Medicina computacional.
- Simulación de datos.

Actualmente las GANs son una de las bases principales de modelos generativos avanzados.

---

# Conclusiones

El desarrollo de esta actividad permitió comprender el funcionamiento interno de una Red Generativa Adversaria y el proceso competitivo existente entre el generador y el discriminador.

Se evidenció que el generador aprende progresivamente a producir imágenes más realistas mediante retroalimentación constante proporcionada por el discriminador.

También se observó que el entrenamiento de GANs puede resultar inestable y sensible a múltiples hiperparámetros, lo cual representa uno de los principales desafíos de este tipo de arquitecturas.

La implementación práctica permitió fortalecer conocimientos relacionados con redes convolucionales, aprendizaje profundo y generación de datos sintéticos.

Finalmente, se concluye que las GANs representan una tecnología fundamental dentro del Deep Learning moderno debido a su capacidad para aprender distribuciones complejas y generar información artificial altamente realista.
