# Trabajo Práctico N°3: Detección de Objetos (Logotipos)

Este trabajo se centra en la detección de un logotipo específico (Coca-Cola) en un *dataset* de imágenes con variaciones extremas de escala, iluminación, perspectiva y oclusión, utilizando técnicas clásicas de visión por computadora (sin *Deep Learning*).

## Estrategia de Solución: Arquitectura Híbrida

Para superar las limitaciones inherentes a cada método clásico por separado (donde SIFT falla en patrones repetitivos y *Template Matching* falla en rotaciones), se desarrolló una **Estrategia Híbrida Generalizada** con mecanismo de *fallback*.

El sistema decide dinámicamente qué algoritmo utilizar basándose en la complejidad de la escena:

```mermaid
graph TD;
    A[Imagen de Entrada] --> B{¿SIFT encuentra<br>geometría válida?};
    B -- Sí --> C["Retornar Detección SIFT<br>(Prioridad: Perspectiva/Rotación)"];
    B -- No --> D["Activar Canny Multiescala<br>(Prioridad: Múltiples Objetos/Pequeños)"];
    D --> E[Aplicar NMS];
    E --> F[Retornar Detecciones Múltiples];
