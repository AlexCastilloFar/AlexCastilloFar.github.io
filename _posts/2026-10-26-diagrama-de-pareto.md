---
title: "Diagrama de Pareto: qué es, cómo hacerlo y ejemplo en Excel"
titulo_corto: "Guía: Diagrama de Pareto con ejemplo"
description: "Qué es el diagrama de Pareto, para qué sirve y cómo hacerlo paso a paso, con un ejemplo real de una línea de envasado y plantilla de Excel."
categoria: Calidad
resumen: "Con el caso de una línea de envasado que pierde botellas mal selladas."
respuesta: "el diagrama de Pareto ordena las causas de un problema de mayor a menor frecuencia y te muestra cuáles explican cerca del 80% de los casos. Así sabes qué atacar primero."
plantilla: ishikawa-pareto
grafico: pareto
historia: "4 de 8 causas explican el 85% de las botellas rechazadas"
---

## ¿Para qué sirve?

- Decidir qué problema resolver primero cuando tienes muchos.
- Justificar con datos una mejora ante tu jefe o tu profesor.
- Comparar el antes y el después de una mejora.

## Ejemplo: botellas mal selladas en una línea de envasado

Durante un mes, el supervisor anotó por qué se rechazaron 138 botellas. Estos son los datos ya ordenados de mayor a menor:

| Causa | Frecuencia | % individual | % acumulado |
|---|--:|--:|--:|
| **Tapas fuera de especificación** | 48 | 34.8% | 34.8% |
| **Cabezal de sellado desgastado** | 35 | 25.4% | 60.1% |
| **Temperatura de sellado inestable** | 22 | 15.9% | 76.1% |
| **Operarios nuevos sin capacitación** | 12 | 8.7% | 84.8% |
| Botellas con rebabas en el cuello | 8 | 5.8% | 90.6% |
| Torquímetro sin calibrar | 6 | 4.3% | 94.9% |
| Humedad alta en la planta | 4 | 2.9% | 97.8% |
| Otros | 3 | 2.2% | 100.0% |

## Cómo hacerlo paso a paso

1. Anota cada causa y cuántas veces ocurrió en el mismo periodo.
2. Ordena de mayor a menor frecuencia.
3. Calcula el % individual: frecuencia ÷ total (48 ÷ 138 = 34.8%).
4. Calcula el % acumulado sumando fila por fila.
5. Grafica barras con la frecuencia y una línea con el % acumulado.
6. Marca el 80%: las causas que quedan antes de esa línea son las **pocas vitales**.

**Resultado:** solo 4 de 8 causas explican el 85% de las botellas rechazadas. Si la empresa cambia de proveedor de tapas y repara el cabezal, ataca más de la mitad del problema.

## Errores comunes

- Mezclar datos de periodos distintos (una semana con un mes).
- Poner "Otros" al inicio: siempre va al final, aunque sea grande.
- Creer que el 80/20 es exacto. Es una guía, no una ley.
