# Semana 8 - Actividad 8  
## Implementación de CNN y Transfer Learning en Clasificación de Imágenes

---

# 1. Objetivo

El objetivo de esta actividad es implementar una **Red Neuronal Convolucional (CNN)** para clasificación de imágenes y compararla con un enfoque de **Transfer Learning**, con el fin de analizar mejoras en rendimiento y generalización.

---

# 2. Dataset

Se utiliza el dataset **CIFAR-10**, el cual contiene:

- 60,000 imágenes en color
- 32x32 píxeles
- 10 clases diferentes

Ejemplos:
- aviones
- autos
- aves
- gatos
- perros

---

# 3. Preprocesamiento

Se aplicaron los siguientes pasos:

- Normalización de píxeles (0 a 1)
- One-hot encoding de etiquetas
- División en entrenamiento y validación

Esto permite:
- Estabilidad en el entrenamiento
- Mejor convergencia del modelo

---

# 4. Modelo CNN Base

La CNN implementada incluye:

- Capas Conv2D para extracción de características
- MaxPooling para reducción dimensional
- Flatten para vectorización
- Dense layers para clasificación

Este modelo aprende características desde cero.

---

# 5. Transfer Learning

Se utiliza **MobileNetV2 preentrenado en ImageNet**.

Características:

- Se congelan las capas base
- Se añade una cabeza clasificadora
- Se adapta al dataset CIFAR-10

Ventajas:

- Mejor generalización
- Menor tiempo de entrenamiento
- Uso de conocimiento previo

---

# 6. Resultados

## CNN Base:
- Buen aprendizaje inicial
- Mayor sobreajuste en validación
- Menor precisión comparativa

## Transfer Learning:
- Mejor estabilidad
- Mayor accuracy
- Mejor generalización

---

# 7. Análisis de resultados

Se observa que:

- La CNN desde cero depende fuertemente del dataset
- Transfer Learning mejora el rendimiento significativamente
- MobileNetV2 permite extraer características más robustas

---

# 8. Conclusiones

- Las CNN son efectivas para extracción de características espaciales
- Transfer Learning mejora el desempeño en datasets pequeños
- El uso de modelos preentrenados reduce el overfitting
- Se evidencia mejor convergencia en Transfer Learning
- Existe un trade-off entre entrenamiento desde cero y reutilización de conocimiento

---

# 9. Ejecución

1. Abrir en Google Colab
2. Ejecutar todas las celdas
3. Comparar métricas entre CNN y Transfer Learning
4. Analizar gráficas y resultados
