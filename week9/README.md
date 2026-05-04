# Semana 9 – Actividad 9

## Data Augmentation y Transfer Learning en Clasificación de Imágenes

### Objetivo

Evaluar el impacto de técnicas de **Data Augmentation** y **Transfer Learning** en el desempeño de modelos de clasificación de imágenes, comparando diferentes configuraciones bajo un mismo dataset.

---

### Dataset

Se utilizó **Fashion MNIST**, un conjunto de 70,000 imágenes en escala de grises (28x28) distribuidas en 10 clases de prendas de vestir.

---

### Modelos implementados

Se entrenaron y compararon cuatro enfoques:

* Modelo CNN base (sin mejoras)
* Modelo CNN con Data Augmentation
* Modelo con Transfer Learning (MobileNetV2)
* Modelo con Transfer Learning + Fine Tuning

---

### Comparación realizada

Se evaluó el desempeño de cada modelo manteniendo constantes las condiciones de entrenamiento, variando únicamente el uso de técnicas de mejora (Data Augmentation y Transfer Learning).

---

### Resultado principal

El uso de **Transfer Learning** mejoró significativamente la precisión del modelo frente al enfoque base, mientras que el **Data Augmentation** contribuyó a reducir el sobreajuste. La combinación con **Fine Tuning** obtuvo el mejor rendimiento general.

---

### Cómo ejecutar

1. Abrir el notebook en Google Colab
2. Ejecutar todas las celdas (Run All)
3. Visualizar métricas, gráficas y comparación final

---

### Estructura del repositorio

```
week9/
│
├── week9.ipynb
└── README.md
```

---

### Conclusión

Las técnicas de Data Augmentation y Transfer Learning permiten mejorar significativamente la capacidad de generalización y desempeño de modelos de Deep Learning en clasificación de imágenes, siendo especialmente útiles en escenarios con datos limitados.

---
