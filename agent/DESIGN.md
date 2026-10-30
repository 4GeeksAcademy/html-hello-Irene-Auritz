# Guía visual de marca y producto

> **Estado:** propuesta de dirección visual para el prototipo. La paleta indicada por el equipo es la única base de color acordada. El nombre, logotipo, tipografías concretas, fotografía y decisiones de identidad aún requieren validación de la empresa. No presentar las propuestas de esta guía como decisiones oficiales de la marca.

## 1. Propósito y contexto

Diseñar una tienda en línea para una marca francesa de *streetwear* de lujo, con interfaz, contenidos y entrega en español. La experiencia debe sentirse editorial, urbana, cuidada y exclusiva sin sacrificar claridad, accesibilidad, facilidad de compra ni rendimiento.

La accesibilidad es un atributo de marca: no es una capa técnica que se añade al final. Cada decisión de tipografía, contraste, composición, navegación e interacción debe facilitar el uso a personas con distintas capacidades.

Esta guía acompaña a `agent/AGENTS.md` (requisitos de implementación) y a `agent/contexto_del_proyecto.md` (alcance de las cinco páginas). En caso de conflicto, respetar los requisitos más recientes del equipo y dejar constancia de la decisión.

## 2. Dirección visual propuesta

### Concepto

**Lujo urbano editorial:** siluetas y prendas con presencia, presentadas con composición sobria, fotografía protagonista, tipografía expresiva pero legible y acentos visuales controlados. La referencia a París debe sentirse contemporánea y sutil; evitar clichés turísticos, banderas y recursos decorativos que no aporten a la marca.

### Atributos buscados

- **Urbano:** prendas, poses y composiciones con carácter, no estética corporativa.
- **Sofisticado:** jerarquía y detalle cuidados; evitar adornos y efectos por defecto.
- **Editorial:** títulos con intención, imágenes amplias y espacio negativo.
- **Accesible:** información clara, contraste suficiente y controles fáciles de identificar y utilizar.

### Principios de composición

1. La prenda y su imagen son protagonistas; la interfaz no debe competir con ellas.
2. Usar el espacio negativo y una retícula consistente en lugar de acumular marcos, sombras y ornamentos.
3. Mantener los acentos rojos escasos y funcionales, no como decoración permanente.
4. Preferir líneas, separadores y tipografía a sombras intensas o tarjetas muy redondeadas.
5. No imitar marcas existentes ni incorporar símbolos cuya procedencia o significado no esté confirmado.

Estos principios son una propuesta para el prototipo y se podrán ajustar al validar la marca.

## 3. Paleta de color

Los cinco valores siguientes son los colores proporcionados por el equipo. Sus usos de interfaz concretos son recomendaciones sujetas a la verificación de contraste y contexto.

| Token sugerido | Valor | Aplicación recomendada |
| --- | --- | --- |
| `color-ink` | `#0C120C` | Fondo oscuro de marca, texto principal sobre superficies claras y áreas de alto peso visual. |
| `color-muted` | `#6D7275` | Texto secundario e iconos inactivos solo cuando el contraste con el fondo sea suficiente. No usar automáticamente para texto pequeño. |
| `color-accent` | `#C20114` | Acción principal, precio promocional o estado destacado; usar de forma contenida y con una etiqueta o texto que comunique el significado. |
| `color-surface` | `#C7D6D5` | Superficies diferenciadas, contenedores o detalles. No asumir que sirve como borde accesible en todos los fondos. |
| `color-paper` | `#ECEBF3` | Fondo claro, texto sobre `color-ink` y superficies de lectura. |

### Reglas de uso

- No añadir colores de marca por conveniencia. Si se necesita un color para estados (error, éxito, aviso), proponerlo, verificar su accesibilidad y pedir aprobación antes de considerarlo parte de la paleta.
- No comunicar estado, disponibilidad, selección o error únicamente con color: acompañarlo con texto, forma, icono con nombre accesible u otra señal perceptible.
- No usar `color-muted` en texto esencial, pequeño o de bajo peso sin comprobar contraste sobre su fondo real.
- No usar el rojo como único indicador de error; reservarlo para el acento aprobado y acompañarlo de una descripción textual.
- Los bordes sutiles pueden no ser suficientes para delimitar controles. Complementarlos con etiquetas, espaciado, forma y estados de foco claramente visibles.
- El equipo mencionó modo claro y modo oscuro, pero no confirmó que la tienda deba ofrecer un selector de tema. Hasta acordarlo, diseñar primero una presentación clara con áreas oscuras de marca; no implementar un conmutador de tema por suposición.
- Antes de aprobar combinaciones, medir el contraste de texto y controles en sus estados normal, hover, foco, seleccionado, deshabilitado y error. Objetivos WCAG 2.2 AA: mínimo 4.5:1 para texto normal, 3:1 para texto grande y 3:1 para componentes y gráficos necesarios para comprender la interfaz. Los valores calculados deben registrarse al definir tokens definitivos; no se presume que una pareja de colores cumple sin medirla.

## 4. Tipografía y texto

### Sistema tipográfico

La dirección tipográfica definida para el prototipo combina una fuente gótica expresiva en títulos con una sans serif de carácter editorial para la interfaz y la lectura.

- **Títulos principales y titulares de campaña:** `Old London`, para aportar una identidad gótica marcada. Reservarla para encabezados breves y tamaños amplios; no usarla en párrafos, controles, precios ni textos pequeños.
- **Sans serif de apoyo:** se propone `Franklin Gothic` por su carácter grotesco/editorial y buena legibilidad, que acompaña la estética gótica sin competir con Old London. Usarla en navegación, subtítulos, etiquetas, botones y textos de producto.
- **Lectura prolongada y formularios:** priorizar una sans serif neutral del sistema para garantizar lectura cómoda. Si Franklin Gothic no está instalada localmente, usar una pila de reserva como `system-ui, Arial, sans-serif`; no cargar fuentes desde CDNs ni servicios externos.
- **Precios y cantidades:** usar la sans serif de interfaz, con cifras fáciles de distinguir y alineación consistente.

La disponibilidad de Old London y Franklin Gothic debe comprobarse en el entorno de entrega. Si no se proporcionan como archivos locales con licencia adecuada, no asumir que están instaladas ni incorporarlas desde una fuente externa: conservar las pilas de reserva y solicitar los archivos aprobados. Si se aprueban fuentes locales, definir sus pesos disponibles y declarar las alternativas en CSS.

### Jerarquía y legibilidad

- Mantener la fuente gótica como acento, no como textura para toda la interfaz. En móvil, comprobar especialmente que las formas ornamentadas sigan siendo legibles y no se confundan entre sí.
- Usar tamaños cómodos, altura de línea suficiente y contraste adecuado; evitar textos largos en mayúsculas, tracking extremo y bloques centrados extensos.
- No distinguir información solo mediante la tipografía: combinar peso, tamaño y posición con etiquetas claras cuando sea necesario.
- Usar español natural, acentos y puntuación correctos. Los nombres oficiales de prendas o colecciones pueden conservarse si el equipo los valida; explicar términos de moda cuando afecten la comprensión.

## 5. Fotografía y contenido visual

- Priorizar las imágenes locales existentes en `IMG/`. No enlazar imágenes, vídeos, iconos, fuentes ni scripts alojados en servicios externos.
- Respetar la intención de cada imagen: moda editorial con contexto y detalle de prenda. Evitar recortes que oculten características relevantes del producto.
- Mantener proporciones y tratamiento coherentes dentro de catálogos y tarjetas; no estirar imágenes. Usar `object-fit` de manera deliberada según la imagen.
- Revisar `IMG/textos-alternativos.md` para asociar cada archivo con su título y texto alternativo. El `alt` debe describir la imagen en el contexto en que se utiliza, sin repetir el título ni añadir referencias editoriales como `[cite: …]`. Si la imagen es decorativa, usar `alt=""`.
- No inventar color, material, ajuste, procedencia ni características que no se puedan confirmar en los recursos o datos del producto.

## 6. Layout y comportamiento adaptable

Diseñar *mobile first*. Evitar scroll horizontal y asegurar que el contenido principal esté disponible sin depender de gestos complejos.

### Retícula

Para listados y rejillas de productos, la distribución objetivo es:

| Tamaño | Columnas |
| --- | ---: |
| Móvil | 1 |
| Tableta | 2 |
| Escritorio | 4 |

La regla de columnas aplica especialmente al catálogo y a colecciones de producto; no se debe forzar sobre formularios, navegación, ficha individual, resumen de compra u otras composiciones que necesiten otra estructura. Usar breakpoints de Tailwind coherentes con el ancho real del contenido y comprobarlos en viewport estrecho, intermedio y amplio.

### Criterios de página

- **Inicio:** una imagen de campaña con jerarquía y llamada a la acción clara; después, bloques de productos reconocibles y fáciles de explorar.
- **Catálogo:** título descriptivo, filtros utilizables con teclado y táctil, resultado de filtros comprensible y cuadrícula de 1/2/4 columnas según el dispositivo.
- **Producto:** imagen y compra como focos principales; en móvil, apilar con la información esencial y la acción de compra fáciles de encontrar. No ocultar selección de talla, precio ni errores.
- **Carrito:** líneas de producto legibles, cantidades editables con controles etiquetados y resumen del pedido claramente diferenciado.
- **Checkout:** formulario por secciones con etiquetas persistentes, instrucciones y errores junto al campo correspondiente; no depender de placeholders como única etiqueta.

## 7. Componentes y estados

### Navegación y pie de página

- Mantener navegación y pie de página consistentes en todas las páginas.
- Incluir enlace para saltar al contenido principal, marca/nombre textual mientras no haya logotipo oficial, enlaces descriptivos y acceso a cuenta/búsqueda solo si su comportamiento está resuelto.
- En móvil, la navegación debe seguir siendo operable con teclado y lector de pantalla. No añadir un menú desplegable que dependa solo de hover.

### Botones y enlaces

- Diferenciar visual y semánticamente acciones principales, secundarias y enlaces.
- Usar verbos específicos en español (por ejemplo, «Añadir al carrito»), áreas táctiles cómodas y foco visible.
- Mostrar estados hover, foco, activo, deshabilitado y carga cuando proceda; el estado no debe depender del color solamente.

### Tarjetas de producto

- Tratar la imagen y el nombre como enlaces identificables; exponer nombre, precio y variante relevante como texto, no solo como contenido incrustado en la imagen.
- Mantener una proporción de imagen consistente en una misma colección y evitar que alturas o precios desalineados dificulten el escaneo.
- No usar toda la tarjeta como un control inaccesible ni anidar enlaces y botones de forma inválida.

### Filtros y formularios

- Asociar cada entrada con una etiqueta; agrupar opciones relacionadas mediante `fieldset` y `legend` cuando corresponda.
- Reflejar selección, cantidad y error con texto accesible y estados semánticos apropiados.
- Conservar foco y valores cuando se muestren errores; no borrar lo que el usuario ya ingresó.

## 8. Iconografía y movimiento

- Preferir iconos SVG locales, pequeños y con propósito; no usar bibliotecas externas ni emojis como sustituto de iconos de interfaz.
- Los iconos decorativos se ocultan de tecnologías de asistencia; los funcionales requieren nombre accesible visible o programático.
- Evitar animaciones innecesarias, parallax y movimiento automático. Respetar `prefers-reduced-motion` y asegurar que ninguna información dependa de una transición.

## 9. Consistencia y mantenimiento

- Reutilizar los mismos tokens de color, escala tipográfica, espaciado, anchos, radios y estilos de foco en todo el sitio.
- Preferir utilidades Tailwind y patrones repetibles; CSS adicional solo cuando Tailwind no resuelva claramente el caso. Sin estilos en línea innecesarios.
- El CDN oficial de Tailwind CSS v4 (`https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4`) está autorizado por `agent/AGENTS.md`; no añadir otros frameworks, CDNs ni recursos externos. Mantener imágenes, fuentes, iconos y demás recursos locales.
- Mantener encabezado, pie de página, botones, campos y tarjetas visualmente coherentes entre Inicio, Catálogo, Producto, Carrito y Checkout.
- No presentar datos ficticios como reales. Para nombres oficiales, precios, IVA, disponibilidad, políticas, contacto y marca, solicitar los datos o señalarlos como contenido de demostración.

## 10. Lista de revisión antes de aprobar un diseño

- [ ] La dirección transmite lujo urbano editorial sin clichés ni imitación de otras marcas.
- [ ] La interfaz y todos los textos están en español, salvo nombres oficiales aprobados.
- [ ] Se usan únicamente recursos locales y la paleta acordada; excepciones tienen justificación y aprobación.
- [ ] La jerarquía visual, los enlaces, las acciones y los estados son comprensibles sin depender solo del color.
- [ ] El contraste de texto, controles, bordes significativos y foco se ha medido sobre sus fondos reales.
- [ ] El flujo se puede recorrer con teclado, el foco es visible y etiquetas/nombres accesibles están presentes.
- [ ] Las imágenes conservan su proporción, tienen recorte intencional y texto alternativo contextual.
- [ ] Rejillas de producto: una columna en móvil, dos en tableta y cuatro en escritorio.
- [ ] No hay desbordamiento horizontal y el orden de lectura funciona en tamaños estrechos y amplios.
- [ ] Los cinco tipos de página comparten sistema visual sin perder claridad en sus tareas particulares.
- [ ] Datos y afirmaciones comerciales no confirmados se identifican como demostración o quedan pendientes.

## 11. Decisiones pendientes de validación

Estas preguntas no bloquean la propuesta visual inicial, pero deben resolverse antes de declarar oficial la identidad:

1. ¿Cuál es el nombre, logotipo y sistema de marca oficial?
2. ¿Qué referencias visuales, valores y límites debe respetar la marca?
3. ¿La tienda tendrá un tema oscuro seleccionable o solo superficies oscuras dentro de una interfaz clara?
4. ¿Se dispone de archivos locales y licencia para Old London y Franklin Gothic? ¿Qué alternativas deben aprobarse si no están disponibles en el entorno de entrega?
5. ¿Qué imágenes son campañas editoriales y cuáles fotografías definitivas de producto?
6. ¿Se aprueba el uso del rojo como acción principal y qué significados funcionales puede representar?
7. ¿Qué datos reales deben aparecer en la tienda: descripción, tallas, precios, moneda, impuestos, disponibilidad y contacto?

Al resolver cada punto, actualizar esta guía para distinguir la decisión aprobada de la propuesta anterior.
