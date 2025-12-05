# Trabajo Práctico N°2: Estimación de Enfoque y Procesamiento de Video

El objetivo de este trabajo es desarrollar y validar métricas capaces de determinar automáticamente el *frame* de mayor nitidez en una secuencia de video.

## Metodologías Evaluadas

Se implementaron y contrastaron dos enfoques teóricos:
1.  **Dominio de la Frecuencia (*Paper* 1):** Análisis del espectro de Fourier (FFT).
2.  **Dominio Espacial (*Paper* 2):** Varianza del Laplaciano.

## Experimentos y Resultados Clave

### 1. Robustez vs. Selectividad
Se observó que mientras la métrica de Fourier genera una curva de respuesta suave y estable, la **Varianza del Laplaciano** es mucho más selectiva (pico agudo), resultando superior para aplicaciones de *autofocus* en tiempo real.

### 2. El Fallo de la Matriz Densa
Al dividir la imagen en una matriz de enfoque de alta resolución (50x50), el punto de máximo enfoque se desplazó erróneamente hacia frames anteriores.
* **Análisis:** Esto demostró que promediar celdas pequeñas hace al algoritmo sensible al ruido de fondo o texturas secundarias, validando la necesidad de seleccionar ROIs inteligentes.

### 3. Efectos Adversos del *Unsharp Masking*
Se intentó mejorar la detección aplicando un filtro de realce (*Unsharp Masking*).
* **Hallazgo:** Contrario a lo esperado, el filtro desplazó el pico de detección del **Frame 111 al Frame 91**.
* **Conclusión:** El realce artificial de bordes amplificó el ruido en frames desenfocados, generando un falso positivo temprano. Esto concluye que no se debe aplicar *sharpening* antes de medir el enfoque.
