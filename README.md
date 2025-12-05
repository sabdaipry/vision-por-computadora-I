# Visión por Computadora I - Portafolio de Trabajos Prácticos

Este repositorio contiene la resolución de los Trabajos Prácticos de la materia **Visión por Computadora I**, correspondiente a la **Especialización en Inteligencia Artificial**.

El objetivo de estos proyectos es explorar y aplicar técnicas fundamentales de procesamiento de imágenes, desde operaciones a nivel de píxel hasta detección de objetos mediante *features* y *template matching*.

## Estructura del Repositorio

### 📂 [TP1: Procesamiento de Color e Histogramas](./TP1)
Enfoque en la manipulación básica de imágenes y análisis estadístico.
* **White Patch:** Implementación robusta del algoritmo de balance de blancos utilizando percentiles para evitar la saturación por brillos especulares.
* **Histogramas:** Análisis comparativo demostrando cómo imágenes con idéntica estadística global pueden tener estructuras espaciales totalmente distintas.

### 📂 [TP2: Detección de Enfoque en Video](./TP2)
Implementación de algoritmos de *Auto-focus* y métricas de nitidez.
* **Métricas:** Comparación entre métodos en el Dominio de la Frecuencia (Transformada de Fourier) y Dominio Espacial (Varianza del Laplaciano).
* **Experimentación:** Análisis de robustez utilizando ROIs, Matrices de Enfoque y filtros de realce (*Unsharp Masking*), con un análisis crítico sobre los desplazamientos de detección introducidos por el ruido.

### 📂 [TP3: Detección de Objetos (Logotipos)](./TP3)
Desafío de detección de patrones en condiciones no controladas (escala, rotación y deformación).
* **Estrategia:** Desarrollo iterativo de un detector basado en **Template Matching Multiescala**.
* **Innovación:** Implementación de estrategias de **Inversión de Contraste** para logos claros sobre fondo oscuro y **Non-Maximum Suppression (NMS)** para detección múltiple.

## Requisitos y Ejecución

El código fue desarrollado en **Python 3** utilizando principalmente las siguientes librerías:
* OpenCV (`cv2`)
* NumPy
* Matplotlib

Para ejecutar los notebooks, se recomienda instalar las dependencias:
```bash
pip install opencv-python numpy matplotlib
