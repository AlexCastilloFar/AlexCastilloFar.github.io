# Contexto del proyecto (para Claude)

Web personal de **Alex**: estudiante de Ingeniería Industrial (UCV, Lima) con más de 8 años en planta y enfoque en análisis de datos. Blog de Ingeniería Industrial + tienda de plantillas de Excel.
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
- Estilo inspirado en Wrike, **siempre con fondo blanco** (sin modo oscuro): azul marino `#162136` para los textos, verde `#00e05c` para los botones (con texto azul marino), tarjetas `#f2f5fa` con esquinas de 20px, botones en forma de pastilla, letra DM Sans. La única zona azul marino es la banda final del inicio.
- Publicar debe ser fácil desde el celular, sin tocar código: se edita en archivos de texto (`_posts`, `_data`, `_config.yml`).

## Estructura
- `_config.yml`: título y enlaces (telegram, tiktok, correo, linkedin).
- `_data/plantillas.yml`: plantillas de la tienda (precios de ejemplo; faltan los finales).
- `_data/herramientas.yml`: herramientas de "La carrera".
- `_posts/`: artículos (molde en `PLANTILLA_ARTICULO.md`; el campo `plantilla` enlaza la plantilla del final).
- `_layouts/` (default, post, plantilla), `_includes/` (tarjetas, miniaturas, foto), `assets/css/style.css`, `assets/img/alex.jpg`.
- Páginas: `index.html`, `carrera/`, `articulos/`, `plantillas/` (detalle por plantilla), `sobre-mi/`.

## Artículos
Claros, con un ejemplo peruano real (bodega, línea de producción, trabajo de la U), pensados para Google (título que la gente busca, respuesta directa al inicio, subtítulos) y con la plantilla relacionada al final.

## Pendiente
- Sección **Cursos**: cursos gratuitos del PIT de la UNI, del canal público de YouTube "PIT 20" y otros. 12 terminados (con videos; Alex pasa los enlaces) y 8 en curso (sin enlaces todavía). Cada curso lleva: qué se aprende, sesiones con video, PDF de apuntes propio, enlace a la inscripción oficial (cursosgratuitos.uni.edu.pe) y una nota de que son apuntes personales, no oficiales y sin logo de la UNI.
  - Terminados: PIT547 BPM con Bizagi, PIT566 Estadística básica con SPSS, PIT612 MS Project, PIT615 Power BI Básico, PIT620 Python Básico, PIT624 SQL 1, PIT432 Análisis de Datos con Excel + IA, PIT443 BPM con Bizagi + IA, PIT503 Gestión por Procesos + IA, PIT511 Lean Manufacturing + IA, PIT518 MS Project, PIT531 Six Sigma + IA.
  - En curso: PIT718 Autodesk Inventor, PIT740 Diseño Gráfico con IA, PIT764 Fundamentos de SSOMA, PIT767 Gestión Financiera con Excel, PIT774 JavaScript Básico, PIT784 Power BI Intermedio, PIT788 Python Intermedio, PIT792 SQL 2.
- Precios finales, enlaces de TikTok y Telegram, videos o GIF de las plantillas, artículos 2 a 6 y el bot de Telegram.
