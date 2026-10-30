# Especificación — Home

- **Funcionalidad:** `001-Home`
- **Estado:** implementado; estilos migrados para priorizar Tailwind CSS
- **Archivo de la página:** `Home.html`
- **Idioma de la interfaz:** español

## 1. Objetivo

Definir la página de inicio de una tienda de *streetwear* de lujo con una presentación editorial, urbana y cuidada. La entrega acordada para esta funcionalidad es una maqueta visual estática, similar a una composición de Figma: debe parecer una página terminada, pero no incluir lógica de tienda ni afirmar que se ha procesado una acción.

Este documento delimita la experiencia y sus criterios de aceptación. La implementación de Home se llevó a cabo tras la instrucción explícita del usuario.

## 2. Alcance

### Incluido

- Una página de inicio adaptable con enfoque mobile-first a móvil, tableta y escritorio, sin desbordamiento horizontal.
- Encabezado de marca y navegación, contenido principal y pie de página coherentes con el sitio.
- Un bloque hero de campaña con imagen protagonista y llamada a la acción visual.
- Secciones de **Novedades** y **Más vendidos**, presentadas como colecciones de tarjetas.
- Uso de las 20 imágenes locales disponibles en `IMG/` dentro de la composición de Home.
- Contenido, enlaces y controles representados de forma estática, sin acciones que aparenten completar compras, búsquedas, inicio de sesión u otros procesos inexistentes. El formulario de contacto del footer solo se habilitará cuando tenga un destino de envío real.
- Buenas prácticas de semántica, accesibilidad y metadatos descritas en este documento.

### Fuera de alcance

- JavaScript, procesamiento de formularios, búsqueda funcional, cuenta de usuario, carrito, checkout, filtros o persistencia de datos.
- Construcción de las páginas de Catálogo, Producto, Carrito o Checkout.
- Servicios, bibliotecas, fuentes, imágenes o estilos remotos salvo el CDN oficial de Tailwind CSS v4 autorizado por `agent/AGENTS.md`.
- Afirmar que la identidad ficticia inventada para la maqueta es la identidad oficial de una empresa real.
- Inventar precios, disponibilidad, políticas, datos de contacto u otros hechos comerciales verificables.

## 3. Estructura y contenido

1. **Encabezado:** identidad textual provisional de marca y navegación clara. Los accesos a otras áreas serán enlaces únicamente si existe un destino local definido; no se presentarán controles sin destino como si fueran funcionales.
2. **Hero:** imagen de campaña local, titular breve en español y llamada a la acción visual. La imagen principal no debe cargarse de forma diferida y debe tener prioridad de descarga, dimensiones intrínsecas declaradas y precarga para favorecer el LCP. El texto no debe afirmar datos comerciales no confirmados.
3. **Novedades:** colección estática de tarjetas con nombres demostrativos, visualmente fácil de explorar; el rótulo forma parte de la maqueta de empresa ficticia y no informa sobre un inventario real.
4. **Más vendidos:** segunda colección estática de tarjetas con nombres demostrativos y jerarquía consistente con Novedades; el rótulo no afirma datos de ventas reales.
5. **Pie de página global:** conservar la misma estructura y estilos al replicarlo en las páginas del sitio. Incluir marca y redes, enlaces de navegación, sección legal, contacto y señales de compra. La empresa ficticia y los datos demostrativos fueron autorizados por el usuario; las secciones legales usan disclosures nativos para explicar el carácter ficticio del contenido. El formulario de contacto es visual, está deshabilitado y no recoge ni envía información mientras no exista un endpoint real. Las formas de pago se nombran como categorías visuales, no como métodos aceptados y verificados.

Las 20 imágenes existentes en `IMG/` deben quedar integradas en la composición de Home exactamente una vez. Su asignación es `FULL.jpg` en el hero y las otras 19 imágenes en las colecciones, respetando el inventario de `IMG/textos-alternativos.md`. No se presentan precios ni disponibilidad; los nombres son etiquetas editoriales de la maqueta y los textos alternativos describen la imagen.

## 4. Dirección visual

- Seguir la dirección editorial urbana de `agent/DESIGN.md`, sin presentarla como identidad oficial validada.
- Paleta acordada: `#0C120C`, `#6D7275`, `#C20114`, `#C7D6D5` y `#ECEBF3`. Comprobar contraste antes de usar cada combinación; no confiar solo en el color para comunicar estados.
- La preferencia tipográfica indicada para la experiencia es Old London en titulares y una sans serif legible en interfaz. El usuario autorizó expresamente Old London para esta maqueta; `FONTS/OldLondon.ttf` está incluido localmente y se carga desde la hoja CSS. No se depende de recursos externos.
- VHS Gothic se utiliza como tipografía de acento en etiquetas breves (eyebrows), navegación y nota de cabecera; Old London se conserva en titulares de exhibición y la sans serif en lectura. La fuente y sus archivos de licencia/atribución se mantienen locales en `FONTS/vhs_gothic/`.
- Mantener imágenes protagonistas, espacio negativo, jerarquía clara y acentos rojos contenidos; evitar clichés turísticos, adornos innecesarios e imitación de marcas existentes.

## 5. Requisitos técnicos y de experiencia

- HTML5 semántico, estructura de encabezados coherente y `lang="es"`.
- Sin JavaScript de aplicación ni manejadores de eventos; solo se permite el script oficial de Tailwind CSS v4 para generar los estilos.
- Priorizar utilidades Tailwind para toda la presentación, incluidos estados y breakpoints. Reservar CSS local para fuentes y tokens compartidos en la capa base.
- Diseñar mobile-first, sin desbordamiento horizontal, con rejillas de una, dos y cuatro columnas en móvil, tableta y escritorio.
- Mantener foco visible, navegación por teclado y alternativas contextuales para las imágenes informativas.
- Incluir título y descripción pertinentes; incorporar Schema.org únicamente con datos verificados y coincidentes con el contenido visible.
- Conservar la presentación terminada, sin avisos técnicos en la interfaz.

## 6. Criterios de aceptación

- [x] Home presenta encabezado, hero, Novedades, Más vendidos y pie de página.
- [x] La composición utiliza las 20 imágenes locales, cada una una sola vez, y sus alternativas se revisaron según el contexto.
- [x] El contenido visible está en español; la identidad y las etiquetas son contenido demostrativo autorizado para la marca ficticia, sin datos comerciales factuales.
- [x] La página es una maqueta estática: no requiere JavaScript de aplicación ni promete completar acciones de tienda; Tailwind genera los estilos mediante su CDN autorizado.
- [x] Usa el CDN oficial de Tailwind CSS v4 como única excepción remota autorizada por las instrucciones del proyecto; imágenes y fuentes permanecen locales.
- [x] La estructura es semántica, el orden de encabezados es lógico y los enlaces tienen propósito comprensible.
- [x] Se puede recorrer con teclado y el foco es visible; las imágenes informativas tienen alternativa contextual.
- [x] La composición usa la retícula de 1/2/4 columnas en breakpoints CSS de `42rem` y `72rem` y se diseñó para evitar desbordamientos.
- [x] Colores y tipografía siguen la dirección visual acordada; las combinaciones de texto usadas se midieron por contraste.
- [x] Los metadatos están presentes; no se añadió Schema.org porque no hay datos estructurados confirmados.

## 7. Hallazgos de la revisión y dependencias

- `FUNCIONALIDADES/001-Home/Home.html` se completó como página estática semántica; enlaza `styles.css`.
- `FUNCIONALIDADES/001-Home/styles.css` contiene exclusivamente las dos fuentes locales y los tokens compartidos en `@layer base`. La presentación, los estados de interacción y los breakpoints se expresan mediante utilidades Tailwind v4 en `Home.html`.
- El footer canónico conserva las clases identificadoras `site-footer`, `footer-main`, `footer-intro`, `footer-nav`, `footer-contact`, `footer-assurance`, `footer-legal-details` y `footer-bottom`. Las páginas futuras deben copiar tanto su estructura como sus utilidades Tailwind, cargar el framework autorizado y enlazar la hoja de fuentes/tokens; las clases identificadoras por sí solas no aplican estilos.
- Las 20 imágenes están documentadas en `IMG/textos-alternativos.md`; sus archivos viven en `IMG/`.
- La fuente autorizada Old London está extraída en `FONTS/OldLondon.ttf`.
- VHS Gothic se carga desde `FONTS/vhs_gothic/vhs-gothic.ttf`; conservar junto a ella `license.txt` y `readme.txt` al redistribuir.
- Las páginas Catálogo, Producto, Carrito y Checkout conservan sus placeholders y quedan fuera del alcance de esta funcionalidad; podrán enlazar la hoja y replicar el contrato común al implementarse.

## 8. Decisiones pendientes, no bloqueantes para esta especificación

- Nombre y logotipo oficiales de una marca real; «NOIR ÉDITION» es solo una identidad ficticia de maqueta.
- Precios, tallas, disponibilidad y demás datos reales de los artículos; no se representan en Home.
- Implementación de destinos de Catálogo, Producto, Carrito y Checkout; sus rutas locales existen, pero siguen siendo placeholders.
- Selección concreta de una sans serif gótica y sus archivos; esta Home usa una pila sans serif del sistema.
- Datos verificables necesarios para completar `Organization` y `WebSite` en Schema.org.
