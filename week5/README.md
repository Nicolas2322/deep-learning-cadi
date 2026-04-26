
# Semana 5 - Implementación de Red Neuronal Multiclase (MLP sin Convolución)

## Objetivo
Implementar y evaluar una red neuronal multicapa (MLP) para un problema de clasificación multiclase, analizando el impacto de los hiperparámetros y técnicas de optimización en el rendimiento del modelo.

---

## Metodología

Se desarrolló una red neuronal completamente conectada (MLP) utilizando TensorFlow Keras, sin el uso de capas convolucionales. Se trabajó con un dataset real de clasificación multiclase y se realizaron múltiples experimentos variando hiperparámetros clave como:

- Tasa de aprendizaje (learning rate)
- Tamaño del lote (batch size)
- Número de épocas
- Tipo de optimizador (Adam y SGD)

Además, se monitoreó el comportamiento del modelo mediante métricas de entrenamiento y validación, junto con visualizaciones gráficas.

---

## Dataset

Se utilizó el dataset **Wine**, el cual contiene:

- 178 muestras
- 13 características numéricas
- 3 clases de salida

Este dataset es adecuado para clasificación multiclase supervisada y no presenta desbalance significativo.

---

## Preprocesamiento

Se aplicaron las siguientes técnicas:

- Normalización de datos usando StandardScaler
- Codificación One-Hot de las etiquetas
- División del dataset en:
  - Entrenamiento (70%)
  - Validación (15%)
  - Prueba (15%)

Estas transformaciones permiten mejorar la estabilidad y el rendimiento del modelo.

---

## Arquitectura del Modelo

Se implementó una red neuronal multicapa con la siguiente estructura:

- Capa de entrada: 13 neuronas
- Capa oculta 1: 64 neuronas (ReLU)
- Capa oculta 2: 32 neuronas (ReLU)
- Capa oculta 3: 16 neuronas (ReLU)
- Capa de salida: 3 neuronas (Softmax)

### Justificación

- ReLU permite evitar problemas de gradientes desvanecidos.
- Softmax es ideal para clasificación multiclase.
- Múltiples capas permiten capturar relaciones no lineales complejas.

---

## Configuraciones Evaluadas

Se realizaron múltiples experimentos:

### Experimento 1
- Optimizador: Adam
- Learning rate: 0.01
- Batch size: 16

### Experimento 2
- Optimizador: Adam
- Learning rate: 0.001
- Batch size: 32

### Experimento 3
- Optimizador: SGD
- Learning rate: 0.01
- Batch size: 16

---

## Resultados

### Comportamiento del entrenamiento

- El optimizador **Adam** mostró una convergencia más rápida y estable.
- **SGD** presentó un aprendizaje más lento y mayor variabilidad.

### Métricas

Se evaluaron:
- Accuracy
- Precision
- Recall
- F1-score

El modelo con mejor desempeño fue:
- Adam con learning rate 0.001 y batch size 32

### Observaciones

- Learning rate alto genera oscilaciones.
- Batch pequeño introduce ruido pero mejora generalización.
- EarlyStopping ayudó a evitar sobreajuste.

---

## Visualizaciones

Se generaron las siguientes gráficas:

- Accuracy vs épocas (entrenamiento y validación)
- Loss vs épocas
- Comparación entre configuraciones
- Matriz de confusión
- Distribución de predicciones

Estas gráficas permitieron analizar:
- Convergencia
- Overfitting
- Estabilidad del entrenamiento

---

## Evaluación del Modelo

El modelo final mostró:

- Alta precisión en clasificación
- Buen balance entre precision y recall
- F1-score consistente en todas las clases

La matriz de confusión evidenció baja tasa de error entre clases.

---

## Análisis de Hiperparámetros

### Learning Rate
- Alto: rápido pero inestable
- Bajo: estable pero más lento

### Batch Size
- Pequeño: mejor generalización
- Grande: entrenamiento más estable pero puede perder precisión

### Optimizador
- Adam: mejor rendimiento general
- SGD: más lento y menos eficiente

### Overfitting y Underfitting
- Overfitting controlado con EarlyStopping
- No se evidenció underfitting significativo

---

## Conclusión

- Las redes MLP son altamente efectivas para problemas estructurados.
- El optimizador Adam demostró ser superior en términos de convergencia y precisión.
- El ajuste de hiperparámetros es crítico para obtener buen rendimiento.
- La validación continua es clave para evitar sobreajuste.
- La combinación de técnicas de optimización y monitoreo mejora significativamente los resultados.

---

## Cómo ejecutar

1. Abrir el notebook en Google Colab o entorno local.
2. Instalar dependencias necesarias:
   - TensorFlow
   - Scikit-learn
   - Matplotlib
3. Ejecutar todas las celdas en orden.
4. Analizar las gráficas y métricas generadas.

---

## Recomendaciones adicionales

Para mejorar aún más el modelo:

- Implementar Dropout para regularización
- Probar más configuraciones de hiperparámetros
- Aplicar Grid Search o Random Search
- Usar validación cruzada
- Evaluar otros datasets más complejos

---
