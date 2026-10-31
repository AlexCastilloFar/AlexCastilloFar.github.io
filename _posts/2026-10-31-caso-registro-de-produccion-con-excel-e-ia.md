---
title: "Caso real: automaticé el registro diario de producción con Excel e IA"
titulo_corto: "Caso real: registro de producción con Excel + IA"
description: "Cómo pasé de horas transcribiendo un cuaderno de producción a un par de minutos, con una base de datos en Excel, SUMAR.SI.CONJUNTO y una foto leída por IA."
categoria: Casos reales
resumen: "Del cuaderno a un reporte automático en minutos, sin errores de digitación."
respuesta: "separé los datos en una tabla limpia (base de datos), hice que el reporte general se llene solo con SUMAR.SI.CONJUNTO y, en vez de digitar el cuaderno, le tomo una foto y una IA me devuelve la tabla lista para pegar. Pasé de horas a un par de minutos."
date: 2026-10-31 06:00:00 -0500
---

> Caso de una planta de manufactura donde trabajo. Por confidencialidad no muestro los formatos ni los datos reales: los ejemplos de abajo son ilustrativos.

## El problema: el cuaderno y la digitación

En planta, la producción de los turnos de día y de noche se anota **a mano en un cuaderno**. Luego alguien tenía que pasar esos números **celda por celda** a un Excel con el reporte general.

El problema era doble:

- Hay **más de 30 tipos de material**, que además cambian según el formato y el mercado. El reporte tenía muchísimas celdas.
- Digitar todo tomaba **horas** y era fácil equivocarse de fila o de número. Un error en el reporte se arrastra a todos los indicadores.

## La solución en 3 pasos

### 1. Una base de datos limpia

Creé una pestaña nueva con una tabla simple, donde **cada fila es un registro** y solo hay 5 columnas:

| Mercado | Mes | Día | Tipo | Peso (kg) |
|---|---|--:|---|--:|
| Local | Octubre | 14 | Tipo A | 125 |
| Local | Octubre | 14 | Tipo B | 75 |
| Exportación | Octubre | 14 | Tipo A | 200 |

*(Datos de ejemplo.)*

Este es el cambio más importante: **los datos se guardan en un solo lugar y en formato de tabla**, no repartidos en un reporte lleno de celdas combinadas.

### 2. El reporte se llena solo

El reporte general ya no se digita. Cada celda tiene una fórmula **SUMAR.SI.CONJUNTO** que busca en la base de datos:

```
=SUMAR.SI.CONJUNTO(Base[Peso]; Base[Mercado]; "Local"; Base[Tipo]; $A5; Base[Día]; C$4)
```

En palabras: *"suma los kilos donde el mercado sea Local, el tipo sea el de esta fila y el día sea el de esta columna"*. Copias la fórmula a todo el reporte y listo: **se llena al 100% de forma automática**.

### 3. De la foto a la tabla con IA

Faltaba lo más pesado: pasar el cuaderno a la base de datos. Ahora:

1. Tomo una **foto del cuaderno** con el celular.
2. Se la paso a una IA con lectura de imágenes (OCR) y le pido que me devuelva una tabla con **los mismos encabezados** de mi base: Mercado, Mes, Día, Tipo, Peso.
3. **Reviso rápido** que los números coincidan con la foto.
4. Copio y pego en la base de datos. El reporte se actualiza solo.

## Resultados

- **De horas a un par de minutos** para registrar la producción del día.
- **Cero errores de digitación:** ya no se escribe número por número.
- Los datos quedan listos para hacer gráficos, tablas dinámicas o un tablero en Power BI.

## Lo que aprendí

- **Primero ordena los datos, después automatiza.** Sin la base de datos limpia, ni la fórmula ni la IA habrían servido.
- **La IA no reemplaza la revisión.** Siempre comparo la tabla con la foto, sobre todo cuando la letra no es clara.
- **No hace falta programar.** Todo esto se hizo con una fórmula de Excel y una herramienta de IA gratuita.

## Cómo aplicarlo en tu negocio o trabajo

Sirve para cualquier registro que se lleve en papel: ventas de una bodega, asistencia, inventario, mermas. La receta es la misma:

1. Define las columnas mínimas que necesitas (fecha, producto, cantidad…).
2. Crea la tabla de base de datos (en Excel: **Insertar → Tabla**).
3. Haz tu reporte con **SUMAR.SI.CONJUNTO** o con una tabla dinámica.
4. Usa la foto + IA para cargar los datos y revisa antes de pegar.
