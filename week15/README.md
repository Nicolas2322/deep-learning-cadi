Análisis de Resultados

El entrenamiento del modelo permitió observar un comportamiento estable tanto en accuracy como en loss. Durante las primeras épocas el modelo presentó una mejora progresiva, logrando aprender patrones importantes del dataset Fashion MNIST.

Las curvas de entrenamiento evidencian que el modelo logra generalizar adecuadamente sin presentar un sobreajuste severo, gracias al uso de capas convolucionales y regularización mediante Dropout.

La matriz de confusión permite identificar cuáles clases presentan mayor dificultad de clasificación. Algunas prendas visualmente similares, como camisetas y camisas, generan errores ocasionales debido a características compartidas.

La integración con Weights & Biases permitió registrar automáticamente todas las métricas del experimento, facilitando la trazabilidad y análisis del entrenamiento.

Estrategia de Model Serving

Una posible estrategia de despliegue para este modelo consiste en crear una API REST utilizando FastAPI.

El flujo de despliegue sería el siguiente:

El usuario envía una imagen.
La API recibe la imagen.
La imagen es preprocesada.
El modelo realiza la predicción.
La API devuelve la clase predicha.

Este enfoque permitiría integrar el modelo en:

Aplicaciones móviles.
Plataformas web.
Sistemas empresariales.
Microservicios de IA.
Conclusiones

El desarrollo de esta actividad permitió comprender que un proyecto de Deep Learning no se limita únicamente al entrenamiento de modelos, sino que involucra múltiples etapas relacionadas con el manejo y trazabilidad de los datos.

La integración de herramientas de monitoreo como Weights & Biases facilita significativamente el análisis de experimentos, permitiendo comparar entrenamientos y mantener un historial organizado de métricas e hiperparámetros.

El modelo convolucional implementado logró un desempeño adecuado sobre el dataset Fashion MNIST, demostrando la capacidad de las CNN para tareas de clasificación de imágenes.

Finalmente, se evidenció la importancia del concepto de Model Serving, entendiendo cómo un modelo entrenado puede convertirse en un servicio consumible por aplicaciones reales mediante APIs o plataformas de inferencia.
