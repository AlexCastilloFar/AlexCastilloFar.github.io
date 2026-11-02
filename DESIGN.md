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
- **Página de Artículos (galería):** botones de área a la izquierda (en celular, píldoras que se deslizan): "Todos" + cada área con su cantidad; el botón activo va relleno en índigo. "Todos" muestra 6 tarjetas en 2 columnas y un botón "Ver más artículos"; un área muestra solo sus artículos. Se puede enlazar directo a un área: `/articulos/#casos-reales`. Cada tarjeta: titular-historia, título, gráfico de muestra (`_includes/grafico.html`, campo `grafico`) y pie técnico.
- **Paleta de acompañamiento (desde nov 2026):** para dar color sin exagerar, solo tonos de la familia del azul: índigo `#3e57da` (principal), índigo profundo `#2c3fb4`, violeta suave `#6a4fe0` (solo en degradados junto al índigo), azul noche `#0d0f2c` y lavanda `#eef1ff` para fondos. Regla: **máximo 2 bloques fuertes por página** (además del pie), alternados con fondos claros. Nada de verde, naranja ni amarillo.
- **Ingeniería Industrial:** estilo Lens (franjas a todo el ancho como el resto de la web; el marco punteado se quitó), portada azul noche con brillo índigo, títulos en dos tonos, tarjetas Mide/Analiza/Mejora en índigo · índigo profundo · violeta, áreas sobre lavanda con burbujas de color, diagrama de nodos (proceso + herramientas, cada nodo enlaza su guía), banda índigo "¿Dónde trabaja?" y cierre con círculo lavanda.
- **Actualización de paleta (pedido de Alex, nov 2026):** solo azules se veía monótono. Se acepta **verde como acento** (estilo DataPulse): botones de compra, checks, etiqueta "Más vendida" y estados de confirmación. Verde para fondo de botón `#15803d` (contraste 5:1 con blanco), hover `#166534`, fondo suave `#e8f7ee`. Violeta `#6a4fe0` como acompañante (degradados de texto y bloques). Sigue prohibido usar verde u otros colores como fondo de secciones grandes.
- **Plantillas (tienda):** portada con texto en degradado índigo→violeta y vista de la plantilla con tarjetas flotantes, 6 beneficios (íconos en índigo/violeta/verde), vista previa con pestañas, catálogo escalable: tarjetas con miniatura en panel degradado, nombre, frase, precio y "Ver detalle" (lleva a la página de la plantilla con el botón de comprar en verde), filtro por categoría y "Ver más" cada 6; etiqueta "Más vendida" con el campo `destacada: true` en _data/plantillas.yml; panel grande con los 3 pasos de compra (estilo Workleap), cómo comprar en 3 pasos + 4 sellos, preguntas frecuentes desplegables y banda final con degradado índigo→violeta.

## 9. PALETA ÚNICA (vigente desde nov 2026 — reemplaza las notas de color anteriores)
Une las paletas que trajo Alex (Workleap, DataPulse y similares). **Toda la web usa estos colores, sección por sección.**

| Rol | Color | Uso |
|---|---|---|
| Texto fuerte y bloques oscuros | Ink Navy `#0c1754` (Midnight `#091135` en degradados) | Títulos, panel del caso, portada de Ingeniería, pie, bloque de contacto |
| Texto | Slate `#36394a` · secundario `#5d6170` | Párrafos y metadatos (AA sobre crema y blanco) |
| Fondo de página | Canvas Cream `#faf9f7` · franjas `#f9f8f6` | Fondo cálido "de papel" |
| Fondo de zona | Lavender Wash `#f5f3ff` / `#eaebf8` | Secciones destacadas, respuesta directa, cierres |
| Bordes | Frost `#e1e9f0` · crema `#f0e9e1` | Tarjetas, divisores |
| Acción | Índigo `#3e57da` | Botones principales y enlaces |
| Compra / confirmación | Verde `#15803d` | Comprar, checks, "Más vendida" |

**Un color por área (fijo en toda la web):** Calidad = cobalto `#2545ff` · Procesos/Mejora = violeta `#6736eb` · Planeamiento/Proyectos = bosque `#046645` · Gestión/Datos = cerúleo `#0074dd` · Casos reales/Producción/Negocios = navy `#0c1754` · eléctrico `#0f77ff` solo decorativo.
- Íconos: fondo tenue + ícono del color de su área (clases `ic-*`, salen solas desde `icon-area.html`).
- Tarjetas en grillas: línea superior de 4px que rota entre los colores de área.
- Portadas de artículos y tarjetas de plantillas: panel con degradado del color de su área + cuadrícula + "pantalla" blanca con el gráfico.
- Títulos en dos tonos: segunda parte en degradado cobalto → violeta.
- **Ingeniería Industrial · herramientas:** diagrama tipo "mejora continua": círculo blanco al centro con el título y 3 barritas de color; 3 herramientas a cada lado, cada una con un círculo blanco, arco de color con flecha hacia el centro y anillo punteado (colores: verde #8cc84b, esmeralda #00c48a, turquesa #00bcc4, celeste #00aef0, azul #1e8ff0, violeta #8b7ff7; solo en gráficos, el texto va en navy). En celular: centro arriba y tarjetas en lista. Mide/Analiza/Mejora: fotos reales en tarjetas claras con degradado suave y letras oscuras.

### Diagramas (nov 2026)
- Paleta de diagramas `--g1…--g6`: verde #8cc84b, esmeralda #00c48a, turquesa #00bcc4, celeste #00aef0, azul #1e8ff0, violeta #8b7ff7. Solo en gráficos; el texto va en navy o en la versión oscura del color (AA).
- **Sobre mí · Trayectoria:** roadmap de 6 etapas que suben (año grande, título, texto), círculo con icono y rampa de colores abajo. Sin "Etapa 1, 2…". En celular: lista vertical.
- **Caso estandarización:** bloque Antes (violeta) vs Después (verde) con medio anillo rotulado (`_includes/antes-despues.html`).
- **Cursos:** tarjeta con el banner oficial del CTIC UNI (`imagen:` en `_cursos`, versión `-800.webp` en la lista), etiqueta de área con color, filtros por área y tarjeta "Cursos en camino" que lleva a la lista de `_data/cursos_en_curso.yml`.
