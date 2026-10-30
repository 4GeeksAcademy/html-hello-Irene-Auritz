# Plan de implementación — Checkout

## Objetivo y alcance vigente

Un solo archivo, `Checkout.html`, reúne datos personales, dirección de entrega y pago como tres pantallas alternables. Solo una está visible a la vez. Esta decisión sustituye tanto la estructura de tres páginas independientes como la presentación de todas las secciones simultáneamente.

Los campos son opcionales y demostrativos. No hay recopilación, transmisión, validación, almacenamiento ni procesamiento. Se agrupan mediante `fieldset` fuera de un formulario de envío para evitar envíos accidentales con Intro. Las acciones de avance y regreso son enlaces internos, no botones de envío.

## Fases

### 1. Unificar estructura y navegación

- Conservar la entrada `Checkout.html`, encabezado, footer, fuentes y tokens compartidos de Home.
- Usar un título principal de Checkout y subtítulos de sección.
- Sustituir la navegación multipágina por enlaces a `#datos-personales`, `#direccion-entrega` y `#pago`.
- Mostrar Datos personales por defecto y únicamente la sección seleccionada por `:target`, mediante variantes Tailwind con `:has()`. Usar `display: none` para excluir del foco y de la lectura accesible los paneles inactivos. No añadir JavaScript ni un indicador fijo de paso actual.

### 2. Integrar controles y recorrido

- Mantener nombre, apellidos, correo y teléfono en la sección de contacto.
- Integrar dirección, complemento, ciudad, código postal, región y país en la sección de entrega.
- Integrar tarjeta, billetera digital y transferencia como opciones nativas ilustrativas, sin marcas ni datos bancarios.
- Añadir enlaces para continuar y volver entre secciones sin exigir datos o selección.
- Añadir a Pago un botón nativo «Confirmar pago» con `commandfor` y `command="show-modal"`, sin envío ni procesamiento.
- Mostrar el agradecimiento en un `dialog` con título VHS Gothic y `::backdrop` desenfocado. Usar enlaces de cierre hacia Inicio y `closedby="none"` para evitar descartarlo sin navegación.
- Mantener tres pantallas: la confirmación visual solicitada es un diálogo superpuesto, no un cuarto paso ni una transacción.
- Conservar las rutas anteriores como redirecciones HTML a las secciones correspondientes y enlaces de respaldo.

### 3. Revisar la página unificada

- Comprobar etiquetas, grupos de controles, IDs únicos, jerarquía y destinos de enlaces internos.
- Comprobar que no hay campos obligatorios, formulario de envío ni scripts aparte del CDN autorizado de Tailwind.
- Revisar errores del editor y disponibilidad de la página en el servidor existente.
- Revisar en navegador avance/regreso sin rellenar, selección de métodos, foco, contraste y adaptación móvil/tableta/escritorio cuando estén disponibles las herramientas.

## Criterios de salida

- Todo el checkout se recorre sin abandonar `Checkout.html` ni rellenar campos, mostrando un solo paso a la vez y conservando temporalmente los valores en sus controles al cambiar de pantalla.
- Los enlaces de sección tienen destinos accesibles mediante teclado y orden lógico.
- La presentación usa Tailwind y estilos globales existentes; no hay CSS local duplicado.
- Se conserva la ausencia de procesamiento, persistencia y captura bancaria. El agradecimiento visual autorizado no implica cobro ni pedido real.
- Comprobar la apertura declarativa del diálogo, el foco, el fondo desenfocado y el regreso a Inicio en un navegador compatible.
- Las comprobaciones que no puedan ejecutarse quedan registradas, no se dan por superadas.