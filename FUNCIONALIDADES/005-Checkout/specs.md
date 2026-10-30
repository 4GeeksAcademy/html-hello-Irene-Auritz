# Especificación — Checkout

## 1. Objetivo

Definir una experiencia de checkout estática, clara y accesible para la tienda de streetwear de lujo. El checkout se compone de **un solo archivo HTML, `Checkout.html`, con tres pantallas alternables**, recorridas en orden mediante enlaces internos. Solo se muestra una pantalla a la vez; no se abren ventanas del navegador:

1. Datos personales.
2. Dirección de entrega.
3. Pago.

La implementación no tendrá lógica de aplicación: no se recopilarán, procesarán ni almacenarán datos, no se enviarán formularios ni se calcularán importes. La petición más reciente autoriza un diálogo de confirmación visual con agradecimiento, sin cobro ni creación real de pedido. Todos los campos serán opcionales y se podrá recorrer el flujo completo sin rellenarlos, sin validación que bloquee el avance.

## 2. Alcance

### Incluido

- Una página para todo el checkout, dentro de `FUNCIONALIDADES/005-Checkout/`.
- Índice numerado de las tres secciones con enlaces a sus destinos, sin indicador fijo de etapa actual.
- Datos personales aparece por defecto. Los enlaces «Continuar» muestran Dirección de entrega y después Pago, ocultando las otras pantallas mediante `:target` y `:has()` expresados con utilidades Tailwind. Los controles ocultos quedan fuera del recorrido de teclado por `display: none`.
- Navegación secuencial con enlaces internos para continuar y volver entre secciones cuando corresponda.
- Formularios HTML semánticos con etiquetas persistentes, controles apropiados, foco visible y diseño adaptable.
- En la etapa de pago, presentación de varios medios de pago como opciones seleccionables visualmente mediante controles HTML nativos. La selección no invocará servicios ni procesará pagos.
- Identidad visual, navegación y footer coherentes con Home y las decisiones documentadas del proyecto.

### Excluido

- JavaScript, procesamiento de formularios, validación personalizada y persistencia de datos entre páginas.
- Integraciones con pasarelas o proveedores de pago, tokenización y captura real de datos bancarios.
- Cálculos de impuestos, envío, descuentos, subtotal o total.
- Afirmaciones de cobro aprobado, transacciones reales o creación efectiva de pedido. El agradecimiento visual expresamente solicitado sí está incluido.
- Datos comerciales inventados (precios, tasas, plazos, condiciones o garantías) presentados como reales.

## 3. Secciones y requisitos

### 3.1 Datos personales

**Propósito:** representar visualmente los campos de contacto del primer paso, sin recoger datos.

**Contenido previsto:**
- Título de página y texto breve que explique el paso.
- Sección `#datos-personales` con encabezado propio y enlace desde el índice.
- Campos etiquetados para nombre, apellidos, correo electrónico y teléfono.
- Acción «Continuar a la dirección» enlazada a `#direccion-entrega`.
- Navegación y footer compartidos.

**Campos:** nombre y apellidos (`text`), correo (`email`) y teléfono (`tel`), todos opcionales, sin `required`. Continuar será un enlace independiente de los campos, no un envío de formulario; tampoco se validarán valores incompletos o incorrectos para avanzar.

### 3.2 Dirección de entrega

**Propósito:** mostrar los campos para que la persona indique dónde desea recibir el pedido.

**Contenido previsto:**
- Título de página y texto breve que explique el paso.
- Sección `#direccion-entrega` con encabezado propio y enlace desde el índice.
- Campos etiquetados para dirección, complemento (opcional), ciudad, código postal, región/provincia y país.
- Enlace a `#datos-personales` y acción «Continuar al pago» enlazada a `#pago`.
- Navegación y footer compartidos.

**Nota:** no preseleccionar país ni prometer cobertura, tarifas o plazos de entrega sin datos aprobados.

### 3.3 Pago

**Propósito:** presentar los medios de pago disponibles en la interfaz y completar visualmente el último paso del checkout.

**Contenido previsto:**
- Título de página y texto breve que explique el paso.
- Sección `#pago` con encabezado propio y enlace desde el índice.
- Opciones distinguibles, etiquetadas y agrupadas mediante `fieldset` y `legend`.
- Enlace «Volver a la dirección de entrega».
- Botón «Confirmar pago» que abre un diálogo nativo de agradecimiento, sin envío ni procesamiento.
- Navegación y footer compartidos.

**Medios de pago representados en la demostración:** tarjeta bancaria, billetera digital y transferencia bancaria. Son categorías genéricas ilustrativas, sin marcas de proveedores, condiciones comerciales ni integraciones.

La selección nativa de una opción solo cambia su estado visual. La pantalla Pago incluye enlaces de regreso y el botón «Confirmar pago», que abre el diálogo mediante `commandfor` y `command="show-modal"`, sin JavaScript. No se exigirá elegir un método ni rellenar campos.

El diálogo muestra «¡Gracias por tu pedido!» en VHS Gothic y un texto cálido de agradecimiento, con el checkout desenfocado mediante su `::backdrop`. Tiene nombre y descripción accesibles. Sus enlaces de cierre y regreso llevan a Inicio. Se usa `closedby="none"` para evitar que Escape o un clic en el fondo lo cierre sin volver a Inicio. Esta interacción requiere soporte del navegador para las acciones declarativas de diálogo; no se ha verificado visualmente todavía.

No incluir campos para número de tarjeta, fecha de vencimiento o código de seguridad mientras no exista un proveedor aprobado y un método seguro de captura. No solicitar ni incluir datos sensibles reales.

## 4. Navegación entre secciones

- Mantener las etapas en este orden: datos personales → dirección de entrega → pago.
- Usar enlaces HTML internos a secciones con IDs únicos y `tabindex="-1"` para permitir foco en sus destinos.
- El índice expone las tres secciones por nombre y número. No declara un paso actual fijo ni necesita JavaScript.
- La navegación interna no recarga la página: los valores permanecen temporalmente en los controles mientras se recorren las secciones, sin guardarse ni transmitirse. Esta limitación interna no se presenta mediante avisos técnicos visibles al usuario.
- La confirmación final es únicamente el diálogo visual autorizado, no una cuarta pantalla ni una operación de compra real.

## 5. Requisitos técnicos y visuales

- HTML5 semántico, idioma español (`lang="es"`), un título principal y metadatos SEO del checkout completo.
- Tailwind CSS v4 como herramienta prioritaria de estilos, usando el CDN oficial autorizado por `agent/AGENTS.md`; CSS local solo para estilos globales imprescindibles.
- Sin JavaScript ni dependencias externas adicionales. Utilizar recursos locales del proyecto.
- Mantener la paleta, tipografía, navegación, footer y estilo de foco coherentes con la referencia de Home y `agent/DESIGN.md`.
- Diseño mobile first, sin desbordamiento horizontal; organizar los campos en una columna en pantallas estrechas y en columnas cuando el ancho lo permita.
- Foco visible, etiquetas asociadas a cada control, agrupación semántica de opciones y texto suficiente para comprender acciones y estados.
- No usar placeholders como única etiqueta, ni transmitir el progreso o la selección únicamente mediante color.

## 6. Criterios de aceptación

- [ ] Un solo archivo contiene tres pantallas del checkout y muestra únicamente la seleccionada; Datos personales es la pantalla inicial.
- [ ] Se puede avanzar y volver mediante enlaces internos con destinos correctos, sin rellenar campos.
- [ ] El título principal, los encabezados de sección y el índice numerado permiten comprender el recorrido.
- [ ] Los campos tienen etiquetas persistentes y tipos HTML apropiados.
- [ ] Los medios de pago se presentan como opciones claramente etiquetadas y su disponibilidad se valida antes de mostrarse como aceptada.
- [ ] No hay JavaScript, envío, procesamiento, persistencia, cálculos ni captura de tarjeta; el diálogo final es únicamente visual.
- [ ] «Confirmar pago» abre el diálogo con fondo desenfocado y título VHS Gothic; los enlaces de cierre llevan a Inicio.
- [ ] La interfaz comparte el sistema visual general de la tienda y funciona en móvil, tableta y escritorio sin scroll horizontal.
- [ ] No se presentan como hechos datos de contacto, impuestos, moneda, políticas, precios, envíos o medios de pago no confirmados.

## 7. Decisiones acordadas para la demostración

1. No hay campos obligatorios ni dirección de facturación adicional en este alcance.
2. No se incluyen campos de tarjeta ni marcas de proveedores; se representan categorías genéricas sin integración.
3. La acción final abre un diálogo visual de agradecimiento; al cerrarlo se vuelve a Inicio, sin enviar datos ni procesar pago.
4. Se omiten condiciones comerciales no confirmadas. La condición de demostración se documenta aquí, no mediante avisos técnicos en la interfaz.

## 8. Documentos relacionados

- `../../agent/AGENTS.md` — requisitos técnicos, de accesibilidad y flujo SDD.
- `../../agent/contexto_del_proyecto.md` — alcance general del sitio y requisitos iniciales de checkout.
- `../../agent/DESIGN.md` — dirección visual propuesta, paleta y principios de interfaz.
