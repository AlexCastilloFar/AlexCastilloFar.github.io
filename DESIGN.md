# DESIGN.md · Sistema visual de Alex Castillo

Guía de diseño de **alexcastillofar.github.io**. Cualquier cambio en la web (hecho por Alex o por una IA) debe seguir estas reglas. El código vive en `assets/css/style.css`.

## 1. Idea central
**Marca personal de un ingeniero industrial**, no una tienda. Primero la persona y la carrera; los cursos y plantillas son "Recursos" dentro de la web.

- **Base:** estilo Synthesia: lienzo blanco, un solo color de acción (índigo), tarjetas con borde fino y sombra suave, y paneles oscuros como "pantallas" para mostrar trabajo.
- **Sello propio (tomado de Devin):** cuadrícula de plano técnico de fondo (`.plano`) y etiquetas técnicas en letra monoespaciada (`.tech`, `.mono`).
- **Prohibido:** el verde tipo Excel como color principal, logos de empresas, testimonios inventados y cualquier dato interno de la empresa donde trabaja Alex.

## 2. Colores
| Token | Valor | Uso |
|---|---|---|
| `--ink` | `#0d0f2c` | Títulos, panel oscuro, botón de filtro activo |
| `--text` | `#333b52` | Texto principal |
| `--muted` | `#5b627c` | Texto secundario (5.6:1 sobre blanco) |
| `--accent` | `#3e57da` | **Único color de acción**: botones principales, enlaces, palabra destacada del título, íconos |
| `--accent-d` | `#2c43b8` | Hover del acento |
| `--glow` | `#8098f9` | Acento solo sobre fondos oscuros |
| `--wash` | `#f5f8ff` | Franjas de fondo alternas, círculos de íconos |
| `--cloud` | `#e6eaf4` | Bordes de tarjetas y divisores |
| `--hair` | `#d1d6e5` | Bordes de botones secundarios |

Reglas:
- Solo un color saturado (el índigo). Nada de segundos colores de marca.
- El índigo no se usa como fondo de secciones grandes; para eso están `--wash` y `--ink`.
- En fondos oscuros: texto blanco o `#c9cfe6` y acentos en `--glow`.

## 3. Tipografía
- **DM Sans** para todo (títulos con peso 500 e interletrado negativo; texto con peso 400).
- **IBM Plex Mono 500** solo para etiquetas técnicas (LEAN / SIX SIGMA…), datos del tablero y números de pasos.
- Escala: h1 38–68px (`clamp`), h2 28–46px, h3 20px, texto 16px, lead 17–19px.
- En celular el interletrado de los títulos es más suave (−0.03em) para que se lea bien.

## 4. Componentes
- **Botón principal** `.btn.btn-ink`: índigo, texto blanco, forma de píldora (radio 999px), alto mínimo 48px.
- **Botón secundario** `.btn.btn-ghost`: blanco con borde `--hair`.
- **Tarjeta** `.card`: blanca, radio 16px, borde `--cloud` + sombra suave. Clicable: `.card-link` (se eleva al pasar el mouse).
- **Íconos**: SVG de trazo en `_includes/icon.html`, dentro de un círculo `.ico-box` (fondo `--wash`, color índigo). Nunca emojis como íconos.
- **Etiqueta** `.tag`: píldora en mayúsculas; `.tag.hot` = índigo con texto blanco.
- **Panel oscuro** `.dark` + `.screen`: para mostrar trabajo (tableros, diagramas). Si los datos son de ejemplo, decirlo.
- **Aviso** `.warn` y **respuesta directa** `.answer`: fondo `--wash` con línea índigo a la izquierda.
- **Sesiones de cursos** `.ses-btn`: botones "▶ Sesión N" que abren YouTube.

## 5. Estructura del sitio
```
Inicio · Ingeniería Industrial · Artículos · Recursos (Cursos, Plantillas) · Sobre mí
```
- Encabezado: **menú flotante tipo cápsula** (blanco translúcido con desenfoque, radio 999px; 20px en celular), **sin logo**, solo el nombre "Alex Castillo" (DM Sans 600) y debajo "INGENIERO INDUSTRIAL" en IBM Plex Mono con espaciado amplio; botón "Contáctame". En celular, menú con botón ☰.
- Pie: descripción, secciones y contacto.

## 6. Reglas de UX (siempre)
1. **Contraste AA:** texto normal ≥ 4.5:1. No usar gris claro sobre `--wash`.
2. **Objetivos táctiles:** todo lo que se toca mide al menos 44px de alto (botones 48px).
3. **Foco visible:** contorno índigo de 3px en navegación con teclado.
4. **Celular primero:** probar a 390px de ancho; nada puede salirse horizontalmente.
5. **Movimiento:** suave y corto (≤ 0.35s); se desactiva con `prefers-reduced-motion`.
6. **Retroalimentación:** todo elemento clicable cambia al pasar el mouse o tocarlo.
7. **Imágenes optimizadas:** fotos de 600px máximo y con texto alternativo.
8. **Textos claros:** frases cortas, verbos de acción en los botones ("Conoce la carrera", "Ver cursos").
9. **Revisión con UI UX Pro Max** antes de grandes cambios (solo sus reglas de UX, no sus estilos).

## 7. Ritmo de la portada (v4)
Cada sección se distingue de la anterior, sin agregar colores de marca nuevos:
1. **Portada** `.hero-sky`: degradado "cielo" (celeste → crema) con cuadrícula de plano y esquinas inferiores redondeadas (40px). Idea de Bevel y Relate.
2. **Cifras** `.stats-band`: franja clara `--wash` con cuadrícula de plano, números 01–04 en índigo y líneas divisorias (se probó oscura y Alex eligió la clara).
3. **Lo que hago** `.feat`: 4 tarjetas sin borde con fondos suaves distintos (lavanda `#eef1ff`, menta `#e7f4ed`, durazno `#fff0e8`, celeste `#e8f1fd`). Idea de Resume.io. Solo fondos: el índigo sigue siendo el único color de acción.
4. **Proyectos de mejora**: fondo `--wash` con plano, panel oscuro (radio 32px) y tarjetas problema → solución → resultado, con punto verde de estado en el resultado.
5. **Artículos**: blanco.
6. **Recursos** `.show`: tarjetas grandes de color (índigo y azul oscuro) con ícono grande de fondo.
7. **Cierre** `.cta-final`: `--wash` con plano y botón de contacto.
8. **Pie**: oscuro `--ink`.

## 8. v5 · Paleta solo índigo y artículos estilo Graphy (31 oct 2026)
- **Fuera el verde y el naranja.** Todo vive en la familia del índigo: `--accent`, `--glow`, `--wash`, `--mist` (#f2f4f8) y blanco. Nada de fondos menta o durazno ni puntos verdes.
- **Dos niveles de superficie (Graphy):** lienzo gris niebla `--mist` + tarjetas blancas con **borde fino** `--line` (rgba(13,15,44,.08)) en vez de sombra. La sombra solo aparece al pasar el mouse.
- **Páginas internas** (cursos, plantillas, recursos, sobre mí, ingeniería): fondo niebla con un "cielo" índigo suave arriba.
- **Artículos:** cabecera con cielo y cuadrícula, píldora de categoría con punto índigo + minutos de lectura, autor con foto; cuerpo en **hoja blanca** sobre niebla; **índice lateral fijo** "En este artículo" (en celular, desplegable) que resalta la sección actual; barra de lectura arriba; pasos numerados en cuadritos índigo; al final "Sigue leyendo" con 3 artículos.
