# Plan de implementación — Home

- **Funcionalidad:** `001-Home`
- **Estado:** ejecutado para la implementación de Home.
- **Especificación de referencia:** [`specs.md`](./specs.md)

## 1. Objetivo del plan

Implementar Home como una página estática, adaptable y visualmente terminada, respetando el alcance y los criterios de aceptación de `specs.md`. Esta funcionalidad también establecerá el patrón común de navegación y pie de página que deberán respetar las demás páginas del sitio.

Este documento registra el enfoque seguido para implementar Home, tras la instrucción explícita del usuario. La implementación se limita a esta funcionalidad.

## 2. Principio compartido: navbar y footer

El navbar y el footer son elementos globales del sitio, no componentes exclusivos de Home. Deben conservar una estructura, orden, contenido, enlaces, nombres accesibles y presentación coherentes en Inicio, Catálogo, Producto, Carrito y Checkout. El footer canónico comprende identidad/redes, navegación de tienda, información legal y ayuda, datos de contacto, formulario deshabilitado hasta disponer de destino real, señales de compra no certificadoras y pie legal. No añadir certificaciones ni garantías comerciales sin evidencia; los métodos de pago son categorías visuales, no una confirmación de aceptación. El usuario autorizó contenido demostrativo de contacto para la marca ficticia, claramente identificado como tal.

Durante la implementación de Home se deberá:

1. Definir una estructura semántica canónica para el navbar y otra para el footer, con sus regiones, elementos, jerarquía y nombres accesibles.
2. En el footer, agrupar marca/redes, enlaces de tienda, información legal, contacto y señales informativas; el formulario solo se habilitará al contar con un endpoint real.
3. Tratar esa estructura como el contrato común que deben seguir todas las páginas. Al implementarse cada página, deberá incorporar el mismo patrón y no crear variantes independientes o incompatibles.
4. Mantener sus estilos globales y estados visuales de forma compartida, de modo que cambios posteriores en navegación o pie de página se puedan aplicar consistentemente al sitio.
5. Asegurar que el patrón funcione en diferentes contextos y tamaños de pantalla, no solo junto al hero de Home: evitar dependencias de dimensiones, fondos o posiciones exclusivas de esta página y comprobar su adaptación junto a distintos contenidos principales.
6. Usar destinos válidos y consistentes para los enlaces. No presentar búsqueda, cuenta ni otros controles como funcionales si no tienen comportamiento implementado y aprobado.

Como el sitio es HTML estático sin JavaScript de aplicación, la convención compartida consiste en copiar el mismo bloque semántico de navbar/footer junto con sus utilidades Tailwind en cada página. Cada HTML debe cargar el CDN oficial autorizado y la hoja local de fuentes/tokens. Las clases identificadoras no sustituyen esas utilidades. No añadir plantillas ni procesamiento de servidor sin aprobación explícita.

La implementación de Home solo establecerá y aplicará el patrón global; **no implica implementar ni modificar las otras cuatro páginas**. La integración de ese patrón en cada página será parte del plan de su funcionalidad correspondiente.

## 3. Secuencia propuesta

### Fase 1 — Preparación y decisiones previas

- Confirmar la aprobación de `specs.md` y de este plan antes de escribir código.
- Revisar la estructura existente de Home y las páginas vecinas para conocer convenciones y destinos locales, sin ampliar el alcance de Home ni modificar otras funcionalidades.
- Mantener estilos globales locales para navbar/footer y detalles propios, pero expresar primero con Tailwind la composición, el layout, el espaciado y los breakpoints; usar únicamente el CDN oficial v4 permitido por `agent/AGENTS.md`.
- Confirmar el contenido/destinos de navegación disponibles y qué elementos deben ser meramente visuales mientras no exista funcionalidad real.
- Definir el inventario de las 20 imágenes y su distribución entre hero, Novedades y Más vendidos, tomando los nombres y alternativas de `IMG/textos-alternativos.md` como referencia.
- Verificar los datos confirmados disponibles para la marca y decidir qué información puede aparecer en metadatos y Schema.org sin inventar datos.

### Fase 2 — Definición del sistema común de página

- Definir el esqueleto semántico compartido: encabezado, navegación, enlace para saltar al contenido, región principal y pie de página.
- Especificar el contrato común del navbar y footer: elementos, orden, enlaces, textos/nombres accesibles, comportamiento adaptable y estados de foco.
- Establecer los estilos compartidos necesarios para que esos elementos se vean correctamente sobre las superficies y contenidos de todas las páginas.
- Registrar el contrato para que las futuras funcionalidades lo implementen de forma idéntica; no crear dependencias de CSS con selectores o dimensiones exclusivos de Home.

### Fase 3 — Maquetación de Home

- Completar `Home.html` con el documento HTML5, idioma español, metadatos y estructura semántica.
- Incorporar el patrón de navbar/footer acordado y el contenido propio de Inicio: hero, Novedades y Más vendidos.
- Distribuir las 20 imágenes locales con recortes deliberados y alternativas contextuales; distinguir las imágenes informativas de las decorativas.
- Aplicar la dirección visual y paleta indicadas en `specs.md`, con tipografías locales autorizadas cuando corresponda.
- Mantener la página estática: sin JavaScript, formularios procesables, controles engañosos, mensajes de éxito ni promesas de acciones inexistentes.
- Añadir Schema.org `Organization` y `WebSite` únicamente si los datos utilizados están verificados y coinciden con el contenido visible.

### Fase 4 — Estilos y adaptación

- Implementar con utilidades Tailwind los layouts y estilos que cubra el framework; reservar CSS local para estilos compartidos, fuentes y detalles editoriales específicos. No cargar recursos remotos excepto el CDN oficial v4 permitido.
- Ajustar el diseño en enfoque *mobile first* y verificar navbar, hero, colecciones y footer en anchos móvil, tableta y escritorio.
- Aplicar una, dos y cuatro columnas respectivamente a las rejillas de productos, cuando corresponda.
- Comprobar contraste, legibilidad tipográfica, foco visible, navegación por teclado, nombres accesibles y ausencia de desbordamiento horizontal.
- Comprobar que las señales de confianza y pago no se interpreten como certificaciones, métodos aceptados o garantías reales sin confirmación; distribuirlas en columnas adaptables.

### Fase 5 — Revisión y aceptación

- Comparar Home con todos los criterios de aceptación de `specs.md`.
- Revisar que navbar y footer cumplan el contrato común y que no estén acoplados al diseño particular de Home.
- Comprobar rutas y enlaces; no dejar enlaces que aparenten una función disponible sin un destino o comportamiento confirmado.
- Validar HTML, recursos locales, alternativas de imagen, metadatos y consistencia de cualquier dato estructurado.
- Registrar las decisiones y pendientes que afecten a la integración futura del patrón global en las otras páginas.

## 4. Entregables previstos (tras aprobar e implementar)

- Home completa en `Home.html`.
- Hoja(s) de estilos locales necesarias, incluida la definición visual compartida de navbar y footer según la ubicación aprobada en la Fase 1.
- Navbar y footer canónicos aplicados a Home y documentados como contrato para que las otras funcionalidades los repliquen sin variaciones.
- Actualización de los artefactos SDD si cambian el alcance o las decisiones aprobadas.

La ubicación exacta de CSS compartido y cualquier cambio adicional de estructura se confirmarán antes de la implementación; este plan no crea esos archivos.

## 5. Condiciones para empezar la implementación

- `specs.md` y este plan revisados y aprobados.
- Decisión documentada sobre el patrón de reutilización del navbar/footer compatible con HTML estático y las reglas del proyecto.
- Destinos de navegación y contenido visible definidos sin afirmaciones de marca no verificadas.
- Disponibilidad local de estilos y tipografías resuelta; extraer las fuentes archivadas solo si la implementación las necesita.
- Tareas de implementación desglosadas en el artefacto SDD correspondiente antes de comenzar a programar.
