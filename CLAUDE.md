# Contexto del proyecto (para Claude)

Web personal de **Alex Castillo** (marca personal): estudiante de Ingeniería Industrial (UCV, Lima) con más de 8 años en planta y enfoque en análisis de datos. Blog de Ingeniería Industrial + tienda de plantillas de Excel.
- Web: https://alexcastillofar.github.io (Jekyll en GitHub Pages, rama `main`).
- Público: estudiantes de Ingeniería Industrial y pequeños negocios en Perú.

## Cómo responderle
- Siempre en **español**, informal y directo, paso a paso y con ejemplos concretos. No es programador y trabaja mucho desde el celular.
- Antes de proponer algo grande, dile si hay una forma más simple. Sé honesto con los riesgos.
- Al terminar, dile qué cambió, qué debe hacer él y qué queda pendiente.
- Nunca le pidas ni muestres tokens o claves.
- En la web **no** pongas su dirección, el nombre de las empresas donde trabaja o trabajó ni datos internos de ellas (se dice "una planta de manufactura").

## Decisiones tomadas
- Todo gratis, sin herramientas de pago. Cobro por Yape o Plin, confirmado a mano. Bot de Telegram (pendiente) en Apps Script con puente en Cloudflare Workers.
- **Diseño: seguir siempre `DESIGN.md`** (estilo Synthesia: blanco + índigo `#3e57da`, DM Sans, tarjetas con borde fino y sombra suave, paneles oscuros como "pantallas"; sello propio: cuadrícula de plano y etiquetas en IBM Plex Mono). Marca personal **Alex Castillo · Ingeniero Industrial**; cursos y plantillas van dentro de "Recursos". **Aplicar siempre reglas de UX** (contraste AA, objetivos táctiles ≥ 44px, foco visible, celular primero, movimiento reducido). Ya no se usa el verde tipo Excel.
- Publicar debe ser fácil desde el celular, sin tocar código: se edita en archivos de texto (`_posts`, `_data`, `_config.yml`).

## Estructura
- `_config.yml`: título y enlaces (telegram, tiktok, correo, linkedin).
- `_data/plantillas.yml`: plantillas de la tienda (precios de ejemplo; faltan los finales).
- `_data/herramientas.yml`: herramientas de "Ingeniería Industrial".
- `_posts/`: artículos (molde en `PLANTILLA_ARTICULO.md`; el campo `plantilla` enlaza la plantilla del final).
- `_layouts/` (default, post, plantilla), `_includes/` (tarjetas, miniaturas, foto), `assets/css/style.css`, `assets/img/alex.jpg`.
- Páginas: `index.html`, `ingenieria-industrial/`, `articulos/` (con filtros por área), `recursos/` (entrada a `cursos/` y `plantillas/`), `sobre-mi/` (con bloque de contacto `#contacto`). Menú: Inicio · Ingeniería Industrial · Artículos · Recursos · Sobre mí.

## Artículos
Claros, con un ejemplo peruano real (bodega, línea de producción, trabajo de la U), pensados para Google (título que la gente busca, respuesta directa al inicio, subtítulos) y con la plantilla relacionada al final.

## Estado actual (1 nov 2026, todo publicado)
- Rediseño completo publicado: Inicio, Ingeniería Industrial, Artículos, Recursos, Plantillas, Cursos y Sobre mí (ver `DESIGN.md`, secciones 7–9 y "Diagramas").
- **Ingeniería Industrial:** franjas a todo el ancho, Mide/Analiza/Mejora con fotos reales (`assets/img/ingenieria/`), herramientas en diagrama tipo "mejora continua" (lee `_data/herramientas.yml`), ¿Dónde trabaja?, tarjeta personal.
- **Sobre mí:** trayectoria tipo roadmap 2017 → hoy (sin "Etapa 1, 2…"), proyectos propios y contacto.
- **Cursos:** 10 terminados en `_cursos/` con banner oficial del CTIC UNI (`imagen:`; versión `-800.webp` para la lista), filtros por área y tarjeta "Cursos en camino" (`_data/cursos_en_curso.yml`). Faltan PDF de apuntes (campo `pdf`) y validar descripciones.
- **Plantillas:** `_data/plantillas.yml`; campo `captura:` = imagen real (si falta, se usa el dibujo `thumb`). Tarjetas solo con la imagen, sin relleno de color.
- **Artículos:** 8 (Pareto, Ishikawa, Gantt, DOP/DAP, 5S y 3 casos reales). El caso de estandarización tiene el bloque Antes vs Después (`_includes/antes-despues.html`). En los casos: nunca nombre de empresa, producto, fórmulas ni porcentajes internos.
- **Vista previa:** se sube a la rama `vista-previa`; una GitHub Action la construye en `vista-previa-site`. Publicar = llevar los cambios a `main`, solo cuando Alex dice "publica".

## Pendiente
- Artículos: estudio de tiempos, OEE, control estadístico.
- Capturas de las plantillas en mejor resolución (pantalla completa) y videos/GIF.
- Precios finales, enlaces de TikTok y Telegram, correo, bot de ventas en Telegram.
- PDF de apuntes de cursos; validar descripciones; LinkedIn.
- Alex debe borrar las ramas `propuesta-v3`, `vista-previa`, `vista-previa-site` cuando ya no se usen.
