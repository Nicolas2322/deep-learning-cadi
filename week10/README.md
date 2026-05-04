# Semana 10 – Actividad 10

## Red Neuronal Siamesa para Reconocimiento de Similitud

### Objetivo

Implementar una **red neuronal siamesa** capaz de comparar pares de imágenes y determinar si pertenecen a la misma clase, comprendiendo el uso de embeddings y funciones de distancia en un espacio latente.

---

### Dataset

Se utilizó **Fashion MNIST** como aproximación al problema de reconocimiento facial.
El dataset fue transformado en pares de imágenes:

* Pares positivos: misma clase
* Pares negativos: clases diferentes

---

### Modelo implementado

Se construyó una arquitectura siamesa compuesta por:

* Red de embeddings (CNN compartida)
* Función de distancia L1
* Capa final sigmoide para predicción de similitud

---

### Comparación realizada

El modelo fue entrenado para clasificar pares como similares o diferentes, evaluando su capacidad de generalización mediante datos no vistos.

---

### Resultado principal

El modelo logró aprender representaciones en un espacio latente, permitiendo distinguir correctamente entre imágenes similares y diferentes, evidenciando un comportamiento consistente en pruebas nuevas.

---

### Cómo ejecutar

1. Abrir el notebook en Google Colab
2. Ejecutar todas las celdas (Run All)
3. Revisar métricas, gráficas y pruebas de similitud

---

### Estructura del repositorio

```id="zaf89r"
week10/
│
├── week10.ipynb
└── README.md
```

---

### Conclusión

Las redes siamesas permiten resolver problemas de comparación entre datos de forma eficiente, siendo especialmente útiles en tareas como reconocimiento facial, verificación de identidad y búsqueda por similitud.

---
