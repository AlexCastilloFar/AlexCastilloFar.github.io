---
title: "Diagrama de Gantt: qué es, cómo hacerlo en Excel y ejemplo"
titulo_corto: "Guía: Diagrama de Gantt con ejemplo"
description: "Qué es un diagrama de Gantt, cómo calcular fechas, predecesoras y ruta crítica, con un ejemplo real de un trabajo grupal de la universidad."
categoria: Planeamiento
resumen: "Con el caso de un trabajo final de la U que siempre se termina a última hora."
respuesta: "el diagrama de Gantt es un cronograma en barras: cada fila es una tarea y cada barra muestra cuándo empieza y cuándo termina. Te dice de un vistazo qué hacer primero, qué va en paralelo y qué tareas no pueden retrasarse (la ruta crítica)."
plantilla: gantt
---

## ¿Para qué sirve?

- Planificar un proyecto antes de empezarlo, no a la mitad.
- Ver qué tareas dependen de otras y cuáles pueden ir al mismo tiempo.
- Saber si vas atrasado comparando el **avance real** con lo planificado.
- Encontrar la **ruta crítica**: las tareas que, si se retrasan un día, retrasan todo el proyecto.

## Las 4 cosas que necesita cada tarea

| Dato | Qué es | Ejemplo |
|---|---|---|
| **Duración** | Cuántos días toma | 3 días |
| **Predecesora** | Qué tarea debe terminar antes | "Recolectar datos" |
| **Inicio y fin** | Se calculan solos a partir de las dos anteriores | 4 al 6 de noviembre |
| **Responsable** | Quién la hace | Lucía |

## Ejemplo: el trabajo final de Gestión de Operaciones

Un grupo de 4 alumnos tiene 3 semanas para entregar un estudio de mejora en una empresa. Siempre terminan amaneciéndose la noche anterior. Esta vez arman el Gantt:

| # | Tarea | Duración | Predecesora |
|---|---|--:|---|
| 1 | Elegir empresa y pedir permiso | 2 días | — |
| 2 | Visita y toma de datos | 3 días | 1 |
| 3 | Marco teórico | 4 días | 1 |
| 4 | Diagnóstico (DOP, Ishikawa, Pareto) | 4 días | 2 |
| 5 | Propuesta de mejora | 3 días | 4 |
| 6 | Redacción final | 2 días | 3 y 5 |
| 7 | Diapositivas y ensayo | 2 días | 6 |

**¿Cuál es la ruta crítica?** Sumamos los caminos posibles:

- 1 → 2 → 4 → 5 → 6 → 7 = 2 + 3 + 4 + 3 + 2 + 2 = **16 días**
- 1 → 3 → 6 → 7 = 2 + 4 + 2 + 2 = 10 días

El camino más largo es la ruta crítica: **16 días**. El marco teórico (tarea 3) tiene **6 días de holgura**, así que puede hacerse con calma en paralelo. En cambio, si la visita a la empresa se retrasa, todo el trabajo se retrasa. Ahora el grupo sabe dónde poner la presión.

## Cómo hacerlo paso a paso en Excel

1. **Lista las tareas** en orden, una por fila.
2. **Pon duración y predecesora** a cada una.
3. **Calcula el inicio:** la primera tarea empieza en la fecha del proyecto; las demás empiezan el día después de que termina su predecesora. En Excel: `=DIA.LAB(fin_predecesora;1)` si no trabajas fines de semana.
4. **Calcula el fin:** `=DIA.LAB(inicio;duración-1)`.
5. **Dibuja las barras:** pon las fechas como columnas y usa formato condicional para pintar la celda si la fecha está entre el inicio y el fin de la tarea.
6. **Marca la ruta crítica** con otro color y actualiza el **% de avance** cada semana.

## Errores comunes

- Poner fechas a mano en vez de calcularlas: cuando una tarea se mueve, tienes que corregir todo.
- No poner predecesoras. Sin ellas no hay ruta crítica.
- Hacer el Gantt el día de la entrega solo para cumplir. Sirve si lo usas desde el inicio.
- Tareas demasiado grandes ("hacer el trabajo"). Divide hasta que cada tarea dure de 1 a 5 días.
