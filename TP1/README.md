# Trabajo Práctico N°1: Balance de Blancos y Análisis de Histogramas
---

Este trabajo práctico aborda problemas fundamentales de la visión computacional: la constancia del color y la representación estadística de las imágenes.

## Objetivos
1. Implementar el algoritmo *White Patch* para corregir desviaciones de color causadas por la iluminación.
2. Analizar la utilidad y limitaciones de los histogramas como descriptores de imágenes.

## Implementación y Hallazgos

### 1. Algoritmo *White Patch* Robusto
Se detectó que la implementación estándar del algoritmo (basada en el máximo absoluto) fallaba en imágenes con reflejos especulares (brillos puros), ya que estos saturan el sensor a 255, anulando la corrección.
* **Solución:** Se implementó una variante estadística que utiliza el **percentil 97/99** como referencia del "blanco verdadero", logrando restaurar los colores naturales incluso en presencia de brillos saturados.

### 2. La "Ceguera Espacial" de los Histogramas
Mediante la comparación de dos imágenes visualmente opuestas (un gradiente suave vs. una flor compleja), se demostró empíricamente que ambas poseen **identidad estadística** (mismo histograma, media y desviación estándar).
* **Conclusión:** Esto evidencia que los histogramas, aunque útiles para analizar iluminación y contraste global, carecen de información espacial, siendo insuficientes por sí solos para tareas de clasificación de objetos o estructuras.
