
# Semana 7 - Actividad 7  
## Convolución de Matrices, Padding y Stride

---

# 1. Objetivo

El objetivo de esta actividad es implementar de forma manual la operación de **convolución 2D**, entendiendo su funcionamiento matemático y su aplicación en imágenes.

Además, se analiza el impacto de dos parámetros fundamentales:

- Padding
- Stride

---

# 2. Concepto de Convolución

La convolución es una operación matemática utilizada en procesamiento de imágenes para extraer características como:

- Bordes
- Texturas
- Patrones

Consiste en deslizar un filtro (kernel) sobre una imagen y realizar una multiplicación elemento a elemento.

---

# 3. Kernel utilizado

Se utiliza un kernel de detección de bordes:

- Permite resaltar cambios bruscos en la imagen
- Es útil para visualizar estructuras

---

# 4. Padding

El padding consiste en agregar ceros alrededor de la imagen.

### Efectos del padding:

- Mantiene el tamaño original de la imagen
- Permite analizar bordes correctamente
- Evita pérdida de información espacial

---

# 5. Stride

El stride define el número de pasos que se mueve el kernel.

### Efectos del stride:

- Reduce el tamaño del output
- Disminuye resolución del feature map
- Reduce complejidad computacional

---

# 6. Resultados obtenidos

Se realizaron tres experimentos:

## 6.1 Sin padding
- La imagen se reduce
- Se pierden bordes
- Menor información espacial

## 6.2 Con padding
- Se mantiene tamaño de salida
- Mejor preservación de bordes

## 6.3 Con stride = 2
- Se reduce resolución
- Se simplifica el feature map
- Menor costo computacional

---

# 7. Análisis de resultados

- El padding mejora la preservación de información en bordes.
- El stride controla la reducción de dimensionalidad.
- La convolución permite extraer características locales importantes.

---

# 8. Conclusiones

- La convolución es fundamental en visión por computador.
- Padding permite controlar la pérdida de información espacial.
- Stride permite controlar la resolución del feature map.
- Existe un trade-off entre detalle y eficiencia computacional.

---

# 9. Ejecución

Para ejecutar el notebook:

1. Abrir en Google Colab
2. Ejecutar todas las celdas
3. Revisar matrices e imágenes generadas
4. Analizar resultados comparativos
