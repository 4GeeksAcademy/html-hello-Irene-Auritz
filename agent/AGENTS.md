# Instrucciones para el proyecto

## Contexto y alcance

Este proyecto consiste en un prototipo de tienda en línea para una marca francesa de *streetwear* de lujo. El desarrollo, la interfaz y los contenidos visibles se redactarán en español. La identidad visual y sus decisiones están documentadas en `agent/DESIGN.md`; el alcance funcional inicial, en `agent/contexto_del_proyecto.md`.

Estas instrucciones deben aplicarse al crear o modificar archivos del proyecto. Si hay una contradicción entre estos requisitos y una decisión anterior, se debe respetar la instrucción más reciente del equipo y señalar la contradicción antes de implementar una solución que la incumpla.

## Requisitos técnicos

- Escribir HTML5 semántico y utilizar los elementos según su propósito: `header`, `nav`, `main`, `section`, `article`, `aside`, `form` y `footer`, cuando correspondan.
- No utilizar JavaScript en ninguna forma: no añadir código inline, archivos `.js`, scripts externos, manejadores de eventos ni frameworks o bibliotecas JavaScript. Construir la experiencia con HTML y CSS.
- Priorizar Tailwind CSS para los estilos. No introducir frameworks de interfaz.
- No cargar recursos ajenos al proyecto: evitar imágenes, scripts, hojas de estilo, bibliotecas y fuentes remotas, incluidos CDNs. Utilizar recursos locales existentes. Si Tailwind aún no está disponible localmente, no añadir un CDN por conveniencia; informar de la necesidad de resolver su configuración local antes de depender de él.
- Mantener el prototipo ligero y evitar dependencias innecesarias.

## Presentación de producto final

- Aunque el entregable sea un prototipo, la página y sus contenidos visibles deben presentarse como una tienda final, cuidada y coherente con la marca.
- No incluir avisos, etiquetas ni textos visibles que digan que el sitio es un prototipo, que los datos son de prueba o que no se recopilan/procesan datos.
- No añadir mensajes de éxito, confirmaciones o comportamientos que impliquen un procesamiento inexistente. Mantener los controles en HTML y CSS sin JavaScript; navegación entre páginas estáticas puede hacerse con enlaces.
- No mostrar en la interfaz notas técnicas ni explicaciones sobre limitaciones de implementación. La ausencia de procesamiento se refleja en el alcance estático de la web, no mediante disclaimers.
- No inventar afirmaciones reales sobre la empresa, certificaciones, políticas, contacto o condiciones legales. Si faltan datos de marca o legales imprescindibles, solicitar esos datos antes de presentarlos como hechos; no sustituirlos por avisos de que el sitio es un prototipo.

## Accesibilidad como principio de marca

La accesibilidad debe reflejarse en las decisiones de diseño y en la implementación, no tratarse como un añadido final.

- Usar estructura semántica, orden de encabezados coherente, nombres accesibles y etiquetas asociadas a los controles de formulario.
- Asegurar navegación y operación con teclado, foco visible, enlaces y botones distinguibles, y estados de interacción comprensibles.
- Mantener contraste suficiente y no transmitir información únicamente mediante el color. Revisar los colores y combinaciones definidos en `agent/DESIGN.md` para todos los estados y superficies.
- Proporcionar texto alternativo contextual para imágenes informativas y `alt=""` para las puramente decorativas. Consultar `IMG/textos-alternativos.md` para relacionar las imágenes locales con sus títulos y descripciones; ajustar el texto si el contexto de uso cambia.
- Usar lenguaje claro en español y evitar controles cuyo propósito dependa exclusivamente de un icono o de instrucciones visuales.

## Diseño adaptable

- Diseñar con enfoque *mobile first* y evitar desbordamientos horizontales.
- Para las rejillas de contenido, usar una columna en móviles, dos columnas en tabletas y cuatro columnas en escritorio. Aplicar esta regla especialmente a las rejillas de productos; no forzarla en formularios u otros componentes cuya estructura requiera una composición distinta.
- Comprobar que navegación, tarjetas, imágenes, filtros y formularios sigan siendo legibles y utilizables en los tres tamaños.

## SEO y datos estructurados

- Aplicar buenas prácticas de SEO en cada página: idioma del documento en español, título y descripción únicos y pertinentes, jerarquía correcta de encabezados, contenido descriptivo y enlaces comprensibles.
- Usar marcado Schema.org en JSON-LD o microdatos donde corresponda, con información que coincida con el contenido visible. Seguir el alcance del proyecto: `Organization` y `WebSite` en Inicio; `Product` y `Offer` en la ficha de producto.
- Mantener el marcado coherente con la información presentada en la página; no incluir en Schema.org afirmaciones falsas sobre la empresa, disponibilidad, políticas o condiciones. Si faltan datos factuales imprescindibles, pedirlos antes de publicarlos.

## Coherencia y recursos

- Mantener consistentes la navegación, el pie de página, la tipografía, los colores, los espacios y los componentes compartidos entre páginas.
- Respetar la guía de marca acordada en `agent/DESIGN.md` y la paleta documentada allí; no introducir una identidad o recursos gráficos nuevos sin aprobación.
- Preferir los archivos locales de `IMG/` y sus descripciones registradas. No depender de servicios externos para que una página se vea o funcione.
- Si un requisito es ambiguo o faltan datos necesarios para una decisión de diseño o contenido, documentar la duda y solicitar definición en lugar de asumir.
