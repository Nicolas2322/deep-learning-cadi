# Semana 11 – Actividad 11

## Predicción de Series de Tiempo con LSTM

### Objetivo

Implementar una **red neuronal recurrente (LSTM)** capaz de aprender patrones temporales en una serie de tiempo y predecir valores futuros a partir de observaciones pasadas.

---

### Dataset

Se utilizó una **serie de tiempo sintética** basada en una señal sinusoidal con ruido, simulando datos reales con comportamiento temporal.

---

### Modelo implementado

Se construyó un modelo basado en:

* Capa LSTM para capturar dependencias temporales
* Capa densa intermedia (ReLU)
* Capa de salida para predicción continua

---

### Proceso realizado

Se aplicaron las siguientes etapas:

* Normalización de datos
* Creación de ventanas temporales (secuencias)
* División en entrenamiento y prueba
* Entrenamiento del modelo
* Evaluación con métricas (MSE y MAE)

---

### Resultado principal

El modelo logró capturar la tendencia general de la serie de tiempo, generando predicciones cercanas a los valores reales y demostrando capacidad de aprendizaje temporal.

---

### Cómo ejecutar

1. Abrir el notebook en Google Colab
2. Ejecutar todas las celdas (Run All)
3. Visualizar métricas y gráficas de predicción

---

### Estructura del repositorio

```id="h73kds"
week11/
│
├── week11.ipynb
└── README.md
```

---

### Conclusión

Las redes LSTM son efectivas para modelar datos secuenciales, permitiendo capturar patrones temporales y realizar predicciones útiles en múltiples aplicaciones reales.

---
