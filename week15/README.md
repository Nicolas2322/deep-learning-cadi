# Semana 15 – Actividad 15: Trabajo Cooperativo sobre Data Journey, Acceso y Manipulación de Datos, Monitoreo y Logging, y Model Serving con Weights & Biases

## Introducción

En el desarrollo de proyectos de Deep Learning y Ciencia de Datos, el entrenamiento de un modelo representa únicamente una parte del ciclo completo de construcción de soluciones inteligentes. En entornos reales, los modelos forman parte de un flujo integral que involucra la adquisición de datos, limpieza, transformación, monitoreo continuo, análisis de métricas y finalmente el despliegue o consumo del modelo en aplicaciones reales.

El objetivo de esta actividad es comprender el flujo completo de trabajo conocido como **Data Journey**, el cual describe cómo los datos son recolectados, procesados, utilizados por un modelo y posteriormente monitoreados durante el entrenamiento y posible despliegue.

Adicionalmente, se implementará un sistema básico de monitoreo y logging utilizando la plataforma **Weights & Biases (W&B)**, herramienta ampliamente utilizada en proyectos de Machine Learning para registrar experimentos, visualizar métricas y comparar ejecuciones de modelos.

La actividad también incluye una aproximación conceptual al proceso de **Model Serving**, entendiendo cómo un modelo entrenado podría integrarse posteriormente en aplicaciones reales mediante APIs, servicios web o plataformas en la nube.

Para el desarrollo práctico se utilizará el dataset Fashion MNIST, junto con una red neuronal convolucional simple implementada en TensorFlow/Keras.

---

# Objetivos de la Actividad

## Objetivo General

Comprender el flujo completo de trabajo en proyectos de Deep Learning, desde el acceso y manipulación de datos hasta el monitoreo del entrenamiento y la aproximación al despliegue de modelos.

## Objetivos Específicos

- Comprender el concepto de Data Journey.
- Cargar y transformar un dataset de imágenes.
- Implementar un modelo de Deep Learning reutilizable.
- Registrar métricas de entrenamiento usando Weights & Biases.
- Analizar el comportamiento del modelo mediante métricas y gráficas.
- Comprender cómo un modelo podría desplegarse en producción mediante Model Serving.
- Documentar correctamente cada etapa del flujo de trabajo.

---

# Descripción del Data Journey

El concepto de Data Journey hace referencia al recorrido completo que realizan los datos dentro de un proyecto de Inteligencia Artificial.

En esta actividad, el flujo de datos sigue las siguientes etapas:

1. Obtención de datos desde TensorFlow Datasets.
2. Carga del dataset Fashion MNIST.
3. Limpieza y normalización de las imágenes.
4. División en conjuntos de entrenamiento y prueba.
5. Entrenamiento del modelo de Deep Learning.
6. Registro de métricas mediante Weights & Biases.
7. Evaluación del modelo.
8. Interpretación de resultados.
9. Aproximación conceptual al despliegue del modelo.

Este proceso permite garantizar trazabilidad, organización y control sobre los experimentos realizados.

---

# Dataset Utilizado

Para esta actividad se utiliza el dataset **Fashion MNIST**, un conjunto de imágenes ampliamente utilizado para clasificación de prendas de vestir.

El dataset contiene:

- 70.000 imágenes en escala de grises.
- Tamaño de imagen de 28x28 píxeles.
- 10 categorías de ropa.
- División oficial entre entrenamiento y prueba.

Las clases presentes en el dataset son:

| Clase | Descripción |
|---|---|
| 0 | T-shirt/top |
| 1 | Trouser |
| 2 | Pullover |
| 3 | Dress |
| 4 | Coat |
| 5 | Sandal |
| 6 | Shirt |
| 7 | Sneaker |
| 8 | Bag |
| 9 | Ankle boot |

---

# Acceso y Manipulación de Datos

La preparación de datos es una de las etapas más importantes dentro del flujo de Machine Learning. Un modelo no puede entrenarse correctamente si los datos no han sido previamente organizados y normalizados.

En esta actividad se realizaron las siguientes operaciones:

## Carga del dataset

El dataset fue cargado directamente desde TensorFlow/Keras utilizando las funciones integradas.

## Normalización

Las imágenes originales contienen valores entre 0 y 255. Para mejorar la estabilidad numérica durante el entrenamiento, se normalizaron los datos a un rango entre 0 y 1.

## Cambio de dimensiones

Se agregó un canal adicional a las imágenes para que pudieran ser procesadas correctamente por las capas convolucionales.

## División de datos

Se mantuvo la división oficial del dataset:

- Datos de entrenamiento
- Datos de prueba

Esto permite evaluar la capacidad de generalización del modelo.

---

# Arquitectura del Modelo Implementado

Se implementó una Red Neuronal Convolucional (CNN) sencilla utilizando TensorFlow/Keras.

La arquitectura contiene:

- Capas convolucionales para extracción de características.
- Funciones de activación ReLU.
- Capas MaxPooling para reducción espacial.
- Capas densas completamente conectadas.
- Capa Softmax para clasificación multiclase.

El modelo fue diseñado para mantener una arquitectura simple pero suficiente para demostrar el flujo completo del proyecto.

---

# Monitoreo y Logging con Weights & Biases

Weights & Biases es una plataforma especializada en seguimiento de experimentos de Machine Learning.

La integración con W&B permite:

- Registrar métricas automáticamente.
- Visualizar curvas de entrenamiento.
- Comparar experimentos.
- Monitorear hiperparámetros.
- Registrar configuraciones del modelo.
- Guardar historial de entrenamiento.

Durante esta actividad se registraron:

- Accuracy de entrenamiento.
- Accuracy de validación.
- Loss de entrenamiento.
- Loss de validación.
- Hiperparámetros utilizados.

Esto permite tener trazabilidad completa sobre el comportamiento del modelo.

---

# Importancia del Monitoreo en Deep Learning

El monitoreo permite detectar problemas como:

## Overfitting

Cuando el modelo aprende demasiado bien los datos de entrenamiento pero falla al generalizar.

## Underfitting

Cuando el modelo no logra aprender correctamente los patrones del dataset.

## Problemas de convergencia

Cuando el loss no disminuye adecuadamente.

## Problemas de estabilidad

Cuando las métricas presentan comportamientos irregulares.

Gracias al monitoreo continuo es posible tomar decisiones sobre:

- Ajuste de hiperparámetros.
- Cambio de arquitectura.
- Incremento de datos.
- Uso de regularización.
- Aplicación de Data Augmentation.

---

# Resultados Obtenidos

Durante el entrenamiento se observó una reducción progresiva de la función de pérdida y un incremento constante en la precisión del modelo.

El modelo logró aprender patrones visuales presentes en las imágenes del dataset Fashion MNIST, alcanzando métricas satisfactorias para una arquitectura simple.

Las gráficas registradas permitieron identificar:

- Estabilidad en el entrenamiento.
- Correcta convergencia.
- Diferencia moderada entre entrenamiento y validación.
- Buena capacidad de generalización.

---

# Aproximación a Model Serving

El proceso de Model Serving hace referencia a la publicación de un modelo entrenado para ser utilizado por aplicaciones externas.

Aunque en esta actividad no se realiza un despliegue completo, se analizan alternativas reales de implementación.

## Posibles estrategias de despliegue

### API REST

El modelo podría exponerse mediante Flask o FastAPI para recibir imágenes y retornar predicciones.

### Contenedores Docker

El modelo podría empaquetarse en un contenedor Docker para facilitar su portabilidad.

### Servicios Cloud

El modelo podría desplegarse en plataformas como:

- Google Cloud AI Platform
- AWS SageMaker
- Azure Machine Learning

### Aplicaciones Web

El modelo podría integrarse en aplicaciones web para clasificación automática de imágenes.

---

# Importancia del Ciclo Completo en Deep Learning

Uno de los principales aprendizajes de esta actividad es comprender que un proyecto de Inteligencia Artificial no termina cuando el modelo alcanza buenas métricas.

El verdadero valor de un sistema inteligente depende de:

- Calidad de los datos.
- Trazabilidad del entrenamiento.
- Capacidad de monitoreo.
- Facilidad de despliegue.
- Mantenimiento del modelo.
- Escalabilidad.

Por esta razón, herramientas como Weights & Biases son fundamentales en entornos profesionales.

---

# Conclusiones

El desarrollo de esta actividad permitió comprender el flujo completo de trabajo dentro de un proyecto de Deep Learning, integrando conceptos de preparación de datos, entrenamiento de modelos, monitoreo de métricas y aproximación al despliegue.

La utilización de Weights & Biases permitió registrar y visualizar el comportamiento del modelo de manera organizada, facilitando el análisis de métricas y la trazabilidad de experimentos.

El modelo convolucional implementado logró obtener resultados adecuados sobre el dataset Fashion MNIST, demostrando capacidad de aprendizaje y generalización.

Se evidenció la importancia del monitoreo continuo durante el entrenamiento, especialmente para detectar problemas relacionados con overfitting, underfitting y estabilidad del modelo.

Finalmente, la actividad permitió comprender que los proyectos de Deep Learning forman parte de un flujo mucho más amplio que incluye datos, entrenamiento, monitoreo y posibles estrategias de despliegue en producción.

---
