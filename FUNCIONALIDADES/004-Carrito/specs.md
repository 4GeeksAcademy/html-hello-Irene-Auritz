# Especificación — Carrito

- **Funcionalidad:** `004-Carrito`
- **Estado:** implementación realizada con tarjetas enlazadas a Producto; pendiente de verificación visual renderizada y cierre de validación
- **Rama comprobada:** `Carrito`
- **Página prevista:** `Carrito.html`
- **Idioma:** español

## 1. Objetivo

Definir una página completa de carrito para la tienda estática de *streetwear* de lujo. La página debe presentar con claridad los artículos, cantidades y desglose de importes, y ofrecer navegación hacia Checkout sin dar a entender que se ha procesado un pedido.

La marca y los datos aquí propuestos son ficticios. El usuario autorizó expresamente inventar datos realistas para completar los datos faltantes de esta funcionalidad. No deberán presentarse como información de una empresa real ni reutilizarse como hechos verificados fuera de esta maqueta.

## 2. Alcance

### Incluido

- Página completa de carrito, no panel lateral ni modal.
- Navbar y footer consistentes con el patrón establecido en `FUNCIONALIDADES/001-Home/`.
- Tres líneas de artículos de ejemplo, con imagen local, nombre, variante/cantidad, precio unitario y subtotal.
- Cada línea se presenta como tarjeta de producto y enlaza por imagen, nombre y enlace explícito a la funcionalidad Producto. Las claves de referencia de cada artículo se reservan para enlazar a tarjetas concretas cuando esas tarjetas existan en Producto.
- Resumen monetario con subtotal antes de IVA, IVA y total con IVA incluido.
- Enlace de navegación a `../005-Checkout/Checkout.html` como continuación del flujo estático.
- Diseño responsive, semántico y accesible, siguiendo `agent/AGENTS.md` y `agent/DESIGN.md`.

### Fuera de alcance

- Lógica dinámica del carrito, persistencia, cambios de cantidad, eliminación o recálculo de importes.
- Procesamiento de pedidos, pagos o datos personales.
- JavaScript, endpoints, backend, dependencias/frameworks JavaScript, CDNs o recursos remotos.
- Crear o modificar la página de Checkout, Catálogo o Producto.
- Afirmaciones comerciales reales sobre disponibilidad, entrega, devoluciones, garantías o servicios.

## 3. Datos ficticios de referencia

Para que el diseño pueda especificar un caso completo y coherente, se propone la siguiente cesta. Los precios son demostrativos, en euros, y no son precios comerciales confirmados.

| Imagen local | Nombre de referencia | Variante mostrada | Cantidad | Precio unitario TTC | Subtotal TTC |
| --- | --- | --- | ---: | ---: | ---: |
| `../../IMG/CHAQUETA.jpg` | Chaqueta de piel bordada | Negro · Talla M | 1 | 900,00 € | 900,00 € |
| `../../IMG/SHIRT.jpg` | Camiseta gráfica de manga larga | Gris · Talla M | 1 | 180,00 € | 180,00 € |
| `../../IMG/WING.jpg` | Vaqueros con gráfico de alas | Negro · Talla 32 | 1 | 300,00 € | 300,00 € |

**Contexto monetario supuesto para la maqueta:** marca ficticia con sede en París, Francia; moneda EUR y una tasa de IVA demostrativa del 20 %, asumida para este ejemplo. Los precios mostrados son TTC (IVA incluido). Al usar importes TTC, el resumen se desglosa así:

- Subtotal sin IVA: **1.150,00 €**
- IVA incluido (20 %): **230,00 €**
- Total: **1.380,00 €**

No se añade importe de envío porque no se ha definido una política ni un coste. La especificación no debe convertirse en afirmación sobre tratamiento fiscal o precio real; si se entrega la tienda con datos comerciales reales, estos valores y el régimen aplicable deberán reemplazarse y verificarse antes.

Los productos, variantes, nombres y precios de esta tabla son propuestas ficticias autorizadas para la maqueta. La descripción visible de cada imagen debe limitarse a lo que realmente muestra el archivo local y a su alternativa contextual; no inferir composición, procedencia, disponibilidad o características técnicas no confirmadas.

## 4. Estructura y contenido de página

1. **Metadatos:** documento HTML5, `lang="es"`, título y descripción únicos pertinentes a la cesta.
2. **Enlace para saltar al contenido principal:** objetivo de fragmento existente.
3. **Encabezado global:** identidad textual y navegación compartida. Marcar Carrito como página actual con `aria-current="page"`.
4. **Main:** un H1 descriptivo, por ejemplo «Tu selección», y una sección de artículos.
5. **Artículos:** cada línea debe agruparse semánticamente, incluir miniatura con `alt` contextual, nombre del producto, variante y cantidad como texto, precio unitario y subtotal de línea. Los valores son estáticos; no presentar selectores de cantidad, eliminar, actualizar o aplicar cupón como controles operativos.
6. **Resumen del pedido:** mostrar subtotal sin IVA, IVA incluido con la tasa indicada en esta maqueta y total TTC, con importes legibles y etiquetas explícitas.
7. **Acción principal:** enlace con texto claro (por ejemplo, «Continuar a la compra») que navegue al archivo local de Checkout. Debe entenderse como navegación entre páginas, no como confirmación o procesamiento de una compra.
8. **Navegación secundaria:** enlace para volver al Catálogo, cuyo destino local está definido aunque esa página siga pendiente.
9. **Footer global:** replicar el patrón de Home y usar la hoja CSS local compartida con la ruta relativa correcta.

No mostrar mensajes de compra completada, reserva, envío confirmado ni estados derivados de operaciones que no existan. Tampoco incluir avisos técnicos sobre que la página sea una maqueta.

## 5. Dirección visual, recursos y tipografía

- Seguir la dirección editorial urbana y paleta descritas en `agent/DESIGN.md` y mantener continuidad con Home.
- Usar HTML semántico y CSS local. El placeholder actual menciona Tailwind por CDN; esa referencia no se debe conservar: `agent/AGENTS.md` prohíbe recursos remotos y prevalece sobre la mención anterior a CDN en `contexto_del_proyecto.md`.
- Puede reutilizarse `FUNCIONALIDADES/001-Home/styles.css` con una ruta relativa adecuada y las clases globales existentes. No copiar código de CDN ni crear una infraestructura de estilos que contradiga el sitio estático.
- Mantener la pila tipográfica y los archivos locales de Home (Old London, VHS Gothic y sans serif de sistema) solo donde sea coherente; reservar las fuentes ornamentales para títulos breves, nunca para importes o lectura prolongada.
- Usar exclusivamente imágenes disponibles en `IMG/`; seguir `IMG/textos-alternativos.md` y ajustar las alternativas al contexto de miniatura de producto.
- No añadir iconos o logotipos de marcas comerciales de pago, certificaciones, sellos ni medios de pago afirmados como aceptados.

## 6. Comportamiento estático

El proyecto prohíbe JavaScript y no dispone de backend. Por tanto:

- La lista, variantes, cantidades e importes son una presentación estática de referencia.
- No habrá campos editables ni botones de incremento/decremento, eliminar, actualizar o recalcular que parezcan procesar acciones.
- La acción principal y el retorno al Catálogo son enlaces de navegación a páginas HTML locales existentes.
- No afirmar que el contenido se conserva entre páginas ni que la cesta se sincroniza.

## 7. Accesibilidad y adaptación

- Usar estructura semántica, jerarquía de encabezados lógica, enlaces descriptivos y `lang="es"`.
- Las miniaturas informativas llevan alternativas breves y contextualizadas; no duplicar innecesariamente texto cercano. Respetar las referencias de `IMG/textos-alternativos.md`.
- Proporcionar contraste suficiente para texto, importes, separadores significativos y foco; el foco de teclado debe ser claramente visible y no depender solo del color.
- Presentar cantidad y variante como texto comprensible, no solo con color o iconos.
- Diseñar mobile-first, evitar desbordamiento horizontal y mantener legibles producto/precio/resumen en pantallas estrechas. No es obligatorio forzar las filas de cesta en una rejilla 1/2/4: dicha regla se aplica a rejillas de productos, no a resúmenes de compra.
- Respetar `prefers-reduced-motion` si se incluyen transiciones.

## 8. Criterios de aceptación

- [x] `Carrito.html` es un documento HTML5 completo en español con metadatos únicos y un H1 claro.
- [x] El encabezado y footer son coherentes con el patrón compartido de Home y sus destinos locales están comprobados.
- [x] Se presentan tres líneas de cesta con miniaturas locales, nombre, variante/cantidad, precio unitario y subtotal.
- [x] Las prendas se presentan como tarjetas enlazadas a la página Producto y llevan claves de referencia estables; Producto aún no contiene tarjetas ni anclas concretas, así que no se crean destinos fragmentarios rotos.
- [x] El resumen muestra subtotal sin IVA, IVA incluido y total TTC; los valores de ejemplo cuadran: 1.150,00 € + 230,00 € = 1.380,00 €.
- [x] Los datos inventados están documentados aquí como contenido ficticio autorizado y no se presentan como hechos comprobados fuera de la maqueta.
- [x] Checkout y Catálogo son enlaces de navegación, no acciones de compra simuladas.
- [x] No hay controles de cambio de cantidad, eliminación o compra que aparenten procesar algo sin lógica real. El formulario compartido del footer permanece deshabilitado.
- [x] No hay JavaScript, CDNs ni dependencias remotas para estilos, fuentes o imágenes. El footer conserva enlaces externos a redes sociales como destinos de navegación.
- [x] Las imágenes y textos alternativos son locales y contextuales; los enlaces tienen foco visible definido en CSS. No se realizó una prueba manual con teclado en navegador.
- [ ] La página es legible y usable en móvil, tableta y escritorio, sin desbordamiento horizontal. Los breakpoints y reglas responsive están definidos y revisados en CSS; queda pendiente confirmar el resultado renderizado en navegador.
- [ ] Se revisa contraste y `git diff --check`; las verificaciones de estructura/rutas y diagnósticos del editor no detectaron errores. El contraste fue revisado por pares de color en CSS, pero no se ejecutó una herramienta de medición; `git diff --check` y la inspección renderizada quedan pendientes.

## 9. Dependencias y decisiones

- La rama comprobada al crear esta especificación es `Carrito`.
- `Carrito.html` y `styles.css` ya contienen la implementación estática; `plan.md` y `tasks.md` documentan su proceso y estado.
- Las rutas de las otras funcionalidades existen, pero sus páginas pueden seguir en estado placeholder.
- `FUNCIONALIDADES/003-Vista-producto/Producto.html` se inspeccionó y continúa siendo un placeholder sin tarjetas de producto ni IDs enlazables. Las tarjetas del carrito enlazan a esa página y exponen claves `data-product-ref` para facilitar la correspondencia al implementar Producto; los enlaces a anclas específicas quedan pendientes de que existan sus destinos.
- Los nombres, variantes, cantidades, precios y cálculo fiscal de esta especificación son valores ficticios aprobados para el ejemplo. Antes de convertirlos en información real del comercio, solicitar datos verificados.
- La implementación debe respetar las reglas vigentes de `agent/AGENTS.md`; en caso de discrepancia con el documento de contexto más antiguo, no usar recursos remotos.

## 10. Registro de verificación de implementación

- Se verificó que la rama activa era `Carrito` y que los destinos de Home, Catálogo, Producto y Checkout, imágenes y hojas CSS locales existen.
- El análisis del editor no reportó errores en `Carrito.html` ni `styles.css`; se revisó el HTML para confirmar `lang="es"`, un H1, tres artículos e IDs/destinos coherentes.
- Se revisaron las reglas mobile-first y breakpoints (42rem y 72rem), así como estilos `:focus-visible`. No hay navegador/renderizador disponible en esta sesión, por lo que no se declara una inspección visual, prueba de scroll horizontal ni prueba de navegación física por teclado.
- La validación final de `git diff --check` no se ejecutó; no se marca como superada.
- En la actualización de tarjetas se comprobaron rama y estado de Git antes de editar; los nuevos enlaces mantienen como destino la página local de Producto. Queda pendiente la correspondencia con anclas específicas hasta que Producto tenga tarjetas reales.
