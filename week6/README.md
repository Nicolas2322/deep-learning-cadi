
# Semana 6 - Actividad 6  
## Regularización, Overfitting y Trade-off Bias-Variance

---

## 1. Objetivo

El objetivo de esta práctica es analizar el comportamiento de una red neuronal comparando:

- Un modelo base (sin regularización)
- Un modelo con regularización (Dropout)

Esto permite observar el fenómeno de overfitting y el impacto de la regularización en la generalización del modelo.

---

## 2. Dataset

Se utiliza el dataset de **Breast Cancer Wisconsin**, un problema de clasificación binaria.

Características:
- 569 muestras
- 30 variables numéricas
- 2 clases (benigno / maligno)

El dataset es adecuado para observar:
- Overfitting en redes densas
- Impacto de regularización

---

## 3. Preprocesamiento

Se aplicaron las siguientes técnicas:

- Normalización con StandardScaler
- División en train, validation y test

Esto asegura:
- Datos escalados para estabilidad del entrenamiento
- Evaluación correcta del modelo
- Prevención de data leakage

---

## 4. Modelos implementados

### Modelo base
- Red neuronal sin regularización
- Mayor capacidad de sobreajuste

### Modelo regularizado
- Dropout (0.3)
- Reduce dependencia de neuronas
- Mejora generalización

---

## 5. Resultados

Se compararon ambos modelos en:

- Accuracy
- Loss
- Precision
- Recall
- F1 Score
- Matriz de confusión

---

## 6. Evidencia de Overfitting

El modelo base muestra:
- Mayor accuracy en entrenamiento
- Menor rendimiento en validación

Esto indica sobreajuste.

El modelo regularizado:
- Menor gap entre train y validation
- Mayor estabilidad

---

## 7. Conclusiones

- El overfitting ocurre cuando el modelo memoriza los datos de entrenamiento.
- Dropout mejora la generalización reduciendo la dependencia entre neuronas.
- La regularización mejora la estabilidad del modelo.
- El trade-off es una ligera reducción en training accuracy pero mejora en test.

---

## 8. Ejecución

Para ejecutar este notebook:

1. Abrir en Google Colab
2. Ejecutar todas las celdas
3. Revisar gráficas y métricas comparativas
