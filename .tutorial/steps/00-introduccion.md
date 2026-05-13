# Paso 0. Introducción

Este laboratorio condensa un recorrido avanzado de SAST con OpenGrep. No está pensado para aprender qué es el análisis estático desde cero, sino para practicar decisiones más exigentes: reglas complejas, trazabilidad de excepciones, integración de resultados y uso operativo de los hallazgos.

## Qué vas a trabajar

Durante el tutorial vas a tocar varios puntos que suelen separar una instalación básica de un programa SAST más maduro:

- reglas custom con lógica más expresiva
- análisis de flujo de datos y relaciones entre archivos
- gestión de falsos positivos sin degradar la señal
- publicación de resultados en formatos reutilizables como SARIF
- quality gates y reporting orientados a operación, no solo a demostración

## Qué problema intenta resolver este laboratorio

En un entorno real no basta con ejecutar un escáner y acumular findings. El problema operativo aparece cuando:

- las reglas son demasiado genéricas o demasiado ruidosas
- nadie sabe cuándo una excepción está justificada o vencida
- el pipeline no convierte hallazgos en decisiones de merge
- los resultados no se pueden explotar para seguimiento y mejora continua

Este tutorial se centra precisamente en esa parte avanzada del trabajo.

## Cómo se recorre el tutorial

Cada paso te pedirá dejar una pieza explícita y revisable en el repositorio. El orden importa: primero construyes criterio sobre reglas y análisis, después integras resultados y finalmente aterrizas gobierno, reporting y cierre del programa.

## Qué conviene tener claro antes de empezar

- una regla más compleja no siempre es mejor; tiene que aportar señal útil
- un falso positivo mal gestionado degrada la confianza en todo el sistema
- SARIF, quality gates y reporting son útiles cuando se conectan con decisiones reales
- una excepción avanzada necesita justificación y vencimiento, no solo una lista de exclusiones

## Siguiente paso

El botón **Empezar tutorial** abre directamente el paso 1.
