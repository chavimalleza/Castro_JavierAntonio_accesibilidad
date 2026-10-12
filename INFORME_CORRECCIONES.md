# Informe de accesibilidad — Unidad 1

## Objetivo
Evaluar tres páginas HTML con WAVE, corregir los problemas de accesibilidad indicados en el enunciado y dejar anotaciones explicativas en el código fuente.

## Resultados registrados en WAVE

| Indicador de WAVE | `ejercicio1.html` | `ejercicio2.html` | `ejercicio3.html` |
|---|---:|---:|---:|
| Errors | 0 | 0 | 0 |
| Contrast Errors | 0 | 0 | 0 |
| Alerts | 0 | 0 | 1 |
| Features | 5 | 8 | 1 |
| Structure | 8 | 5 | 2 |
| ARIA | 4 | 1 | 1 |

La alerta del ejercicio 3 corresponde al vídeo HTML5 y requiere revisión manual. En la comprobación realizada con Live Server, la pista de subtítulos se muestra sobre el vídeo. La alerta puede mantenerse porque WAVE no puede comprobar automáticamente toda la calidad, sincronización y cobertura de los subtítulos.

## Correcciones realizadas

### 1. `ejercicio1.html` — Página informativa sobre mascotas
- Se mantiene el elemento `<title>` dentro de `<head>` y se ha aclarado mediante un comentario su función.
- Se establece `lang="en"`, ya que el contenido principal de la página está redactado en inglés.
- Se añaden textos alternativos descriptivos al logotipo y a las imágenes de perros, gatos y peces, en el idioma del contenido.
- Se conserva un encabezado principal `<h1>` y encabezados `<h2>` para las secciones de cada animal.
- Se identifican las secciones mediante `aria-labelledby` y la navegación mediante `aria-label`.

### 2. `ejercicio2.html` — Formulario de contacto
- Los campos Nombre y Apellidos tienen etiquetas `<label>` vinculadas a sus controles mediante `for` e `id`.
- Las opciones de género tienen etiquetas individuales y están agrupadas con `<fieldset>` y `<legend>`.
- El desplegable de animal favorito tiene una etiqueta vinculada.
- Se conservan el nombre visible del botón de envío, el foco de teclado visible y los atributos de autocompletado.

### 3. `ejercicio3.html` — Vídeo y subtítulos
- El vídeo dispone de controles de reproducción.
- Se activa la pista `<track>` con `kind="captions"`, `srclang="en"` y la ruta `./subtitles/friday.vtt`.
- Se añade un comentario en el código que explica la relación de la pista con la pauta WCAG.
- Se ha comprobado mediante Live Server que los subtítulos aparecen durante la reproducción.

## Relación con WCAG

- **1.1.1 — Contenido no textual:** textos alternativos en imágenes informativas y logotipo.
- **1.2.2 — Subtítulos (grabados):** pista de subtítulos para el vídeo pregrabado.
- **1.3.1 — Información y relaciones:** estructura de encabezados, secciones y agrupación de campos.
- **2.4.6 — Encabezados y etiquetas:** encabezados y etiquetas que describen su propósito.
- **2.4.7 / 2.4.11 — Foco visible / foco no oculto:** se mantiene un indicador visible de foco en el formulario; la comprobación completa requiere revisión manual.
- **3.3.2 — Etiquetas o instrucciones:** campos de formulario identificados con etiquetas.
- **4.1.2 — Nombre, función y valor:** controles de formulario con nombres accesibles y opciones de radio agrupadas.

## Conclusión

La evaluación automática presenta cero errores y cero errores de contraste en las tres páginas. El ejercicio 3 conserva una alerta asociada al vídeo HTML5, que debe interpretarse como una solicitud de revisión manual y no como un error automático confirmado.

Las correcciones documentadas mejoran la estructura semántica, la identificación de imágenes y campos, y el acceso a los subtítulos. Para concluir una evaluación completa WCAG, además del análisis de WAVE, se deben realizar pruebas manuales de teclado, foco, contenido alternativo y sincronización/cobertura de los subtítulos.
