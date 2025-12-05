# Trabajo Práctico N°3: Detección de Objetos (Logotipos)

Este trabajo se centra en la detección de un logotipo específico (Coca-Cola) en un *dataset* de imágenes con variaciones de escala, iluminación y perspectiva, utilizando técnicas clásicas de visión sin *Deep Learning*.

## Estrategia de Solución

Se desarrolló un algoritmo de ***Template Matching* Multiescala** que evolucionó a través de varias iteraciones para superar las dificultades del *dataset*.

### Características del Algoritmo Final
1.  **Búsqueda Multiescala:** Implementación de una pirámide de imágenes (*resizing* progresivo) para garantizar la invarianza a la escala.
2.  **Invarianza de Contraste (Doble Chequeo):** Se identificó que el fallo principal en las detecciones iniciales se debía a la inversión de polaridad (letras blancas sobre fondo rojo vs. *template* negro sobre blanco). Se solucionó implementando una búsqueda paralela con el *template* normal e invertido.
3.  ***Non-Maximum Suppression* (NMS):** Algoritmo para limpiar detecciones redundantes en el escenario de múltiples objetos.

## Análisis de Resultados y Limitaciones

### Logros
* Se logró una detección robusta y precisa en imágenes con logotipos planos o con rotaciones leves (Ítem 1).
* El sistema es capaz de generalizar y encontrar múltiples instancias del objeto sin ajuste manual de parámetros.

