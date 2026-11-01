# Plan de implementación — Carrito

- **Funcionalidad:** `004-Carrito`
- **Estado:** plan ejecutado en parte; Tailwind CSS v4 y tarjetas de producto integrados, verificación visual y cierre pendientes
- **Especificación:** [`specs.md`](./specs.md)
- **Rama comprobada:** `Carrito`

## 1. Objetivo del plan

Desarrollar la página estática de Carrito descrita en `specs.md`: una vista completa, visualmente coherente con Home, accesible y adaptable, que presente tres artículos ficticios y un resumen de importes coherente, sin simular edición del carrito, cálculos en vivo ni procesamiento de compra. Las prendas se presentan como tarjetas enlazadas a Producto. Producto todavía es un placeholder sin tarjetas ni fragmentos destino, por lo que se usan claves `data-product-ref` para correspondencia futura y no se enlazan anclas inexistentes. Tailwind CSS v4 se añadió después de actualizar `agent/AGENTS.md` para permitir expresamente su CDN oficial; los estilos específicos se migran a utilidades Tailwind, conservando el CSS compartido de marca. La inspección visual renderizada permanece pendiente.

Este documento organiza el trabajo, sus dependencias y su estado. La implementación se encuentra en `Carrito.html`; este plan no es el código ejecutable.

### Migración a Tailwind sin rediseño

Se trasladan todos los estilos específicos de Carrito a utilidades Tailwind CSS v4 y se elimina su hoja `styles.css`. Se conservan los valores originales de colores, espaciado, tamaños, proporciones, interacciones y puntos de corte de 42rem y 72rem. Se mantiene la hoja compartida de Home sin modificar para fuentes, tokens, navegación y pie. «Tu selección» utiliza Old London; «Prendas seleccionadas» y «Resumen del pedido», VHS Gothic. La autorización del CDN en `agent/AGENTS.md` prevalece sobre las restricciones históricas de este plan. La comparación visual en navegador queda pendiente si no hay navegador disponible.

## 2. Principios de implementación

- Respetar la especificación de Carrito y las reglas de `agent/AGENTS.md`; si aparece una contradicción, detenerse, documentarla y resolverla antes de codificar.
- Mantener el alcance en `FUNCIONALIDADES/004-Carrito/`; no modificar Checkout, Catálogo, Producto, Home ni recursos compartidos salvo que una dependencia lo requiera y se apruebe expresamente.
- Reutilizar el contrato visual/semántico de navegación y pie de Home replicando el markup estático y enlazando CSS local compartido. No introducir una plantilla, backend ni JavaScript.
- No reutilizar el CDN de Tailwind del placeholder. No usar herramientas, hojas de estilo, fuentes o imágenes remotas.
- Tratar productos, cantidades, variantes, precios y contexto de IVA como datos ficticios autorizados para la maqueta, no como hechos comerciales reales.
- Hacer que los enlaces operativos sean navegación entre archivos existentes; no mostrar acciones que sugieran modificar o procesar el carrito.

## 3. Secuencia de trabajo

### Fase 1 — Preparación y revisión de dependencias

1. Confirmar la rama con `git branch --show-current`; aceptar `Carrito` o `feature/carrito`, sin cambiar de rama silenciosamente.
2. Revisar `specs.md`, `Carrito.html`, las rutas de destino y el contrato de Home antes de modificar archivos.
3. Confirmar que la especificación y este plan están aprobados. Si se cambian artículos o montos, actualizar primero `specs.md` y volver a comprobar el desglose.
4. Identificar las rutas relativas correctas desde `004-Carrito` a `IMG/`, Home CSS, Catálogo y Checkout.
5. Mantener Tailwind CDN fuera del resultado. Si se requiere Tailwind, detenerse para resolver una instalación local aprobada; en caso contrario usar CSS compartido ya disponible y estilos locales mínimos específicos de Carrito.

**Salida de fase:** dependencias y destinos confirmados, datos de ejemplo fijados y alcance aprobado.

### Fase 2 — Estructura semántica HTML

1. Sustituir el contenido placeholder de `Carrito.html` por un documento HTML5 completo en español, con metadatos únicos, título/descripción pertinentes y un destino válido para el enlace de salto al contenido.
2. Incorporar navbar compartido de Home con Carrito marcado como actual, preservando nombres accesibles y enlaces relativos.
3. Añadir `main` con un solo H1, encabezado de cesta y listado semántico de tres artículos.
4. Para cada artículo, presentar imagen local contextual, nombre, variante, cantidad como texto, precio unitario TTC y subtotal TTC. No añadir botones o inputs inactivos de eliminar, modificar cantidad, cupón o actualizar.
5. Crear el resumen del pedido con subtotal sin IVA, IVA incluido al 20 % y total TTC claramente etiquetados y correctamente calculados a partir de los precios especificados.
6. Añadir enlace principal a `../005-Checkout/Checkout.html` para continuar la navegación y enlace secundario a `../002-Catalogo/Catalogo.html`. Presentarlos como enlaces, no como acciones que completen la compra.
7. Replicar al final el footer común de Home con sus destinos ajustados a la ubicación de Carrito; conservar estructura, etiquetas y navegación coherentes.
8. Mantener todo el contenido visible en español y no añadir notas técnicas sobre restricciones, estados de éxito o afirmaciones comerciales no verificadas.

**Salida de fase:** HTML completo y enlazado, todavía pendiente de estilo específico y validación.

### Fase 3 — Estilos y composición responsive

1. Enlazar la hoja CSS local compartida de Home mediante la ruta relativa correcta para obtener tokens, tipografía, navbar, footer y estilos globales.
2. Añadir estilos específicos de la vista solo si los estilos compartidos no cubren el layout de carrito; preferir una hoja local específica si evita alterar componentes de otras páginas.
3. Diseñar mobile-first: en viewport estrecho priorizar nombre, variante, cantidad e importes en una composición vertical o apilada; en pantallas amplias organizar líneas y resumen con jerarquía clara.
4. Evitar forzar una rejilla de producto 1/2/4 en las filas del carrito; conservar el contenido compacto, sin desbordamiento horizontal.
5. Usar la tipografía de interfaz para importes y lectura; reservar Old London/VHS Gothic para encabezados breves donde ya se emplean en Home.
6. Mantener la paleta de `agent/DESIGN.md`, espacios generosos y separadores discretos; verificar contraste del texto, importes, controles de navegación y foco sobre cada superficie.
7. Evitar animación innecesaria; si se introduce, respetar `prefers-reduced-motion`.

**Salida de fase:** carrito con estilo coherente en móvil, tableta y escritorio, sin dependencias externas.

### Fase 4 — Auditoría y validación

1. Validar estructura HTML, `lang="es"`, un H1, jerarquía de encabezados, labels si existieran, IDs únicos y destino del skip link.
2. Verificar las rutas relativas de las tres imágenes, CSS compartido, enlaces a Catálogo/Checkout y enlaces del footer.
3. Revisar que las alternativas de imagen sean breves, contextuales y coherentes con `IMG/textos-alternativos.md`.
4. Recalcular importes independientemente: 900 € + 180 € + 300 € = 1.380 € TTC; desglosar el precio TTC al 20 % como 1.150 € sin IVA + 230 € de IVA incluido. No añadir envío.
5. Buscar y descartar `<script>`, dependencias remotas/CDN, formularios de pedido, controles que aparenten editar, marcas de pago, certificaciones y promesas de procesamiento.
6. Revisar teclado, foco, contraste, ampliación y presentación en anchos representativos de móvil, tableta y escritorio; confirmar ausencia de scroll horizontal.
7. Ejecutar `git diff --check` y las herramientas de validación disponibles. Registrar lo verificado y cualquier limitación visual; no declarar pruebas visuales si no se usó navegador.
8. Actualizar los criterios y estado de `specs.md` solo con resultados confirmados; registrar el trabajo completado en el artefacto de tareas de Carrito una vez exista y tras autorización de implementación.

**Salida de fase:** evidencia de aceptación y lista de pendientes; no crear commits ni cambiar de rama como parte del plan.

## 4. Archivos previstos al implementar

- `Carrito.html`: estructura de página, contenido y enlaces locales.
- Hoja de estilo específica de Carrito solo si el CSS compartido no satisface el layout; el uso/ubicación debe acordarse antes de alterar estilos globales.
- `specs.md`: cambios solo si la revisión aprobada modifica alcance o datos.
- `plan.md`: este plan, actualizado con decisiones confirmadas o cambios de secuencia.
- `tasks.md`: artefacto de seguimiento que deberá crearse/revisarse antes de empezar la implementación, con tareas comprobables.

No se prevén recursos nuevos, JavaScript, dependencias, procesamiento de carrito ni cambios a páginas vecinas.

## 5. Dependencias y bloqueos

- Aprobación de `specs.md` y este plan.
- Permanecer en rama `Carrito` o `feature/carrito` durante la implementación.
- Disponibilidad de la hoja compartida de Home y confirmación de su ruta relativa, sin modificarla.
- Confirmar qué navegación global se replica tal cual; cualquier búsqueda/cuenta solo puede incluirse si existe comportamiento resuelto.
- Los datos de muestra se consideran autorizados para la maqueta, pero deben permanecer identificados como ficticios en la documentación y no presentarse como precios o tratamiento fiscal reales.
- Checkout y Catálogo son destinos HTML existentes, pero pueden seguir siendo placeholders; el enlace solo ofrece navegación estática.

## 6. Condiciones para comenzar a programar

- La especificación y este plan han sido revisados y aprobados.
- Existe un `tasks.md` propio de Carrito con tareas y verificaciones acordadas.
- La rama activa corresponde a Carrito.
- Los paths locales y los límites de CSS compartido están confirmados.
- Se conserva el alcance estático: no JavaScript, no CDN, no edición/recalculo aparente y ningún procesamiento de compra.
