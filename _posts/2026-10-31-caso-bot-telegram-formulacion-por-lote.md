---
title: "Caso real: un bot de Telegram que calcula la materia prima de cada lote"
titulo_corto: "Caso real: bot de Telegram para formulación"
description: "Cómo hice con Python un bot de Telegram que lee la fórmula en Excel y calcula la materia prima de cada lote con sus saldos. Se usa a diario en planta."
categoria: Casos reales
resumen: "Un asistente en Telegram que los operarios usan a diario para calcular cada lote."
respuesta: "hice con Python un bot de Telegram que lee la hoja de formulación en Excel. El operario escribe qué va a preparar, cuántos kilos y qué saldos tiene, y el bot le responde cuánto de cada materia prima debe agregar en cada olla. Se usa a diario en planta."
date: 2026-10-31 05:00:00 -0500
---

> Caso de una planta de manufactura donde trabajo. Por confidencialidad no muestro las fórmulas, los productos ni los porcentajes reales: los números de abajo son de ejemplo.

## El problema: cálculos a mano en cada lote

Cada producto tiene su **fórmula**: un porcentaje de cada materia prima. Antes de preparar un lote, el operario tenía que calcular a mano:

- En **cuántas ollas** dividir el pedido, porque cada olla tiene una capacidad máxima.
- **Cuánto de cada materia prima** va en cada olla.
- Cuánto aportan los **saldos**: material sobrante de lotes anteriores que se reaprovecha y cambia las cantidades a agregar.

Hacerlo con calculadora toma tiempo y se presta a errores, y un error en la fórmula significa un lote fuera de especificación.

## La solución: un asistente en Telegram

Hice un bot con **Python** que funciona dentro de Telegram, la app que los operarios ya usan en el celular:

1. **Lee la hoja de formulación** en Excel, la misma que ya usaba la planta. Si cambia una fórmula, solo se actualiza el Excel.
2. El operario escribe un mensaje normal, como lo escribiría a un compañero: el producto, los kilos y, si tiene, los saldos.
3. El bot entiende el mensaje (aunque esté abreviado o en varias líneas) y responde con el detalle **olla por olla**.

### Ejemplo (números ficticios)

> **Operario:** Producto X 300 kg, tengo saldo de 10 kg de producto Y
>
> **Bot:** Son 300 kg → 3 ollas de 100 kg. En cada olla agrega: materia prima A 94.00 kg, B 4.000 kg, C 2.000 kg. El saldo de producto Y ya aporta parte de A y B, así que en la primera olla agrega menos…

## Reglas que el bot respeta

- **Mínima cantidad de ollas:** reparte el total en partes iguales sin pasar la capacidad máxima.
- **Precisión:** redondea cada materia prima con los decimales que se usan en planta.
- **La fórmula debe salir exacta:** si los saldos aportan más de algún material del que pide la fórmula, el bot **no da un resultado equivocado**. Propone reducir el saldo hasta que cuadre y pregunta si el operario está de acuerdo.
- **Solo personas autorizadas:** responde únicamente a una lista de usuarios y saluda a cada uno por su nombre.

## Resultados

- **Lo usan a diario** los operarios de planta.
- El cálculo de un lote, incluso con saldos, sale **en segundos**.
- Menos riesgo de error humano en la preparación.
- La fórmula oficial sigue en un solo lugar, el Excel, así que todos calculan con la misma información.

## Lo que aprendí

- **La mejor herramienta es la que la gente ya usa.** No hubo que instalar nada ni capacitar en un sistema nuevo: todos tenían Telegram.
- **Las reglas del negocio importan más que el código.** Lo más difícil no fue programar, sino entender bien cómo se trabajan los saldos y los casos especiales junto con los operarios.
- **Un bot no reemplaza el criterio del operario:** lo ayuda a no equivocarse en los números.

## ¿Se puede hacer sin ser programador?

Sí, con paciencia. Necesitas:

1. Un bot creado con **@BotFather** en Telegram (te da una clave que **nunca** debes compartir).
2. Python con la librería `python-telegram-bot` y `openpyxl` o `pandas` para leer el Excel.
3. Una computadora o un servidor que lo tenga encendido en el horario de trabajo.

Más adelante publicaré una guía paso a paso para hacer un bot sencillo.
