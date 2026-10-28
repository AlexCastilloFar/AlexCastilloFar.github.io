# Alex Industrial

Blog de Ingeniería Industrial + tienda de plantillas de Excel. Web hecha con Jekyll y publicada gratis en GitHub Pages.

## Cómo publicar un artículo nuevo desde el celular

1. Abre este repositorio en el navegador del celular (o en la app de GitHub).
2. Entra a la carpeta `_posts`.
3. Pulsa **Add file → Create new file**.
4. Ponle de nombre: `AAAA-MM-DD-nombre-del-articulo.md`
   Ejemplo: `2026-11-02-diagrama-de-ishikawa.md` (sin tildes, ni ñ, ni espacios).
5. Copia todo el contenido de `PLANTILLA_ARTICULO.md`, pégalo y reemplaza los textos.
6. Pulsa **Commit changes**. En 1 o 2 minutos el artículo aparece en la web.

### Qué significa cada campo de arriba
| Campo | Para qué sirve |
|---|---|
| `title` | Título del artículo (como lo busca la gente en Google) |
| `titulo_corto` | Texto del aviso "Nuevo" en el inicio |
| `description` | Lo que Google muestra debajo del título |
| `categoria` | Etiqueta: Calidad, Planeamiento, Procesos, Gestión, Negocios |
| `resumen` | Texto de la tarjeta del artículo |
| `respuesta` | La respuesta directa del recuadro inicial |
| `plantilla` | Plantilla que se recomienda al final: `ishikawa-pareto`, `gantt` o `cotizador` |

### Formato del texto
- `## Subtítulo` crea un subtítulo.
- `**texto**` pone el texto en negrita.
- `- algo` crea una lista con viñetas; `1. algo` crea una lista numerada.
- Para una imagen: súbela a `assets/img/` y escribe `![descripción](/assets/img/nombre.png)`.

## Cómo agregar un curso o una sesión
- **Nueva sesión:** abre el archivo del curso en `_cursos/`, copia un bloque `- titulo / video` y pega el enlace de YouTube (sirve cualquier enlace de YouTube).
- **Curso nuevo:** en `_cursos/` crea `pit000-nombre-del-curso.md` y pega el contenido de `PLANTILLA_CURSO.md`.
- **Apuntes en PDF:** sube el PDF a `assets/pdf/` y escribe su ruta en el campo `pdf` del curso.
- **Cursos en curso:** se editan en `_data/cursos_en_curso.yml`.

## Otros cambios fáciles
- **Precios y textos de las plantillas:** `_data/plantillas.yml`
- **Enlaces de Telegram, TikTok y correo:** `_config.yml`
- **Tu foto:** sube una imagen cuadrada con el nombre `alex.jpg` a `assets/img/`
- **Herramientas de "La carrera":** `_data/herramientas.yml`
