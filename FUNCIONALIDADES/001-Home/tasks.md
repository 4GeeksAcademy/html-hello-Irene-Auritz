# Tareas de implementación — Home

- **Funcionalidad:** `001-Home`
- **Estado:** implementación de Home completada; integración en otras páginas pendiente de sus funcionalidades.
- **Referencias:** [`specs.md`](./specs.md) · [`plan.md`](./plan.md)
- **Alcance:** registra las tareas y verificaciones realizadas para Home. No amplía el alcance a otras funcionalidades.

## Cómo usar esta lista

Cada tarea reúne un resultado coherente y comprobable, preservando suficiente contexto para poder completarla sin fragmentar el trabajo en pasos mecánicos demasiado pequeños. Las tareas se completaron en orden, tras la instrucción del usuario de iniciar la implementación.

## A. Aprobación y preparación

- [x] **A1. Revisar y aprobar los artefactos SDD de Home.** Confirmado al iniciar la implementación por instrucción del usuario: `specs.md` y `plan.md` describen el alcance estático, los criterios de aceptación y la relación entre el patrón global de navbar/footer y Home.
- [x] **A2. Inspeccionar la estructura y los destinos disponibles.** Revisados `Home.html`, los cuatro HTML vecinos y los recursos del proyecto. Las otras páginas son placeholders, pero sus rutas locales están definidas; no se modifican en esta funcionalidad. No hay CSS ni Tailwind configurado localmente.
- [x] **A3. Resolver la estrategia de estilos compartidos.** La hoja canónica de navbar/footer residirá en `FUNCIONALIDADES/001-Home/styles.css`, enlazada desde Home y disponible para que las páginas futuras la referencien con rutas relativas. Se usará CSS local sin CDN, JavaScript ni bibliotecas externas.
- [x] **A4. Cerrar contenido y decisiones visuales necesarias para Home.** Por indicación del usuario, la marca es ficticia y se puede inventar su nombre y textos editoriales. Se usa «NOIR ÉDITION» como identidad de maqueta y los títulos «Novedades» y «Más vendidos», definidos para Home. `FULL.jpg` será el hero y las otras 19 imágenes se repartirán entre ambas colecciones, sin repetir archivos; las etiquetas y alternativas seguirán `IMG/textos-alternativos.md`. Se usará Old London, cuyo uso autorizó el usuario, y una sans serif de sistema legible para lectura; no se empleará VHS Gothic en párrafos ni controles.

## B. Contrato de componentes globales

- [x] **B1. Definir el contrato semántico y accesible del navbar y footer.** Navbar: enlace de marca, navegación a Inicio, Catálogo, Producto, Carrito y Checkout, enlace de salto al contenido y estado de página actual. Footer: marca/redes SVG locales, navegación, enlaces a aviso legal/privacidad/cookies, datos de contacto ficticios autorizados y etiquetados como tales, formulario visual deshabilitado hasta conectar un servicio y señales informativas de compra. No añadir certificaciones o garantías inventadas ni presentar categorías de pago como métodos aceptados.
- [x] **B2. Establecer el patrón visual global y su regla de reutilización.** La estructura canónica se implementa en Home con las clases CSS `site-header`, `site-nav`, `site-main`, `site-footer` y `footer-*`; estilos en `FUNCIONALIDADES/001-Home/styles.css`, enlazables desde páginas futuras mediante rutas relativas. El footer no depende del hero y su contrato se registra en `specs.md`/`plan.md`; las demás páginas no se modificaron.

## C. Estructura y contenido de Home

- [x] **C1. Completar la estructura base de `Home.html`.** Documento HTML5 en español con metadatos pertinentes, jerarquía de encabezados y regiones semánticas base verificados.
- [x] **C2. Incorporar el navbar y footer canónicos en Home.** Home incluye navegación común y el pie global con información legal, contacto ficticio autorizado, redes, señales de compra y formulario accesible pero deshabilitado mientras no exista un endpoint; Catálogo, Producto, Carrito y Checkout quedan para sus funcionalidades.
- [x] **C3. Maquetar hero, Novedades y Más vendidos.** Home contiene el hero editorial y las dos secciones de colección, con textos en español y llamadas de navegación a destinos locales existentes.
- [x] **C4. Integrar las 20 imágenes locales con tratamiento contextual.** Los 20 archivos locales aparecen exactamente una vez entre hero y colecciones; cada imagen informativa tiene `alt` contextual y las tarjetas usan recorte uniforme por CSS. Las descripciones se contrastaron con `IMG/textos-alternativos.md`.
- [x] **C5. Aplicar la dirección visual acordada.** Se usa la paleta y dirección editorial de `specs.md`, Old London local en titulares, VHS Gothic en etiquetas breves/navegación y sans serif del sistema en lectura. Se conservan los archivos de licencia y atribución junto a VHS Gothic.
- [x] **C6. Añadir Schema.org solo con información verificada.** No se añadió `Organization` ni `WebSite`: no hay datos estructurados confirmados para esos tipos. No se inventan datos y el marcado queda pendiente de información verificable.

## D. Estilos y adaptación

- [x] **D1. Implementar estilos locales para Home y sus componentes globales.** `styles.css` define estilos locales para navbar, footer, hero y colecciones; los estilos compartidos usan clases canónicas y no requieren recursos remotos. No se modifican las otras páginas; estas podrán enlazar esta hoja al implementarse.
- [x] **D2. Adaptar la composición a móvil, tableta y escritorio.** CSS mobile-first: rejilla de 1 columna, 2 columnas desde `42rem` y 4 desde `72rem`; navegación y cabeceras se envuelven en pantallas estrechas, y el footer cambia de disposición por breakpoint. No se fijan anchos mínimos en las tarjetas.
- [x] **D3. Asegurar legibilidad, accesibilidad visual y uso por teclado.** Se midió contraste de combinaciones de texto; en el footer nuevo: papel/tinta 16.02:1, gris claro/tinta 14.35:1, papel/fondo de campos 14.12:1 y gris claro/fondo de campos 12.65:1. Los enlaces tienen señal hover y foco visible; el formulario tiene etiquetas y fieldset accesible, pero permanece deshabilitado sin endpoint. Se mantiene el skip link y `prefers-reduced-motion`.

## E. Validación y cierre

- [x] **E1. Validar comportamiento estático y enlaces.** Confirmado: sin JavaScript ni dependencias externas, y el formulario queda deshabilitado hasta tener endpoint; enlaces locales apuntan a destinos existentes, los fragmentos legales resuelven y las redes apuntan a páginas oficiales. Las páginas destino siguen siendo placeholders fuera de alcance.
- [x] **E2. Revisar estructura, contenido y recursos.** `lang="es"`, un H1, jerarquía de encabezados, metadatos y rutas locales comprobados; parser HTML estándar sin errores estructurales, 20 imágenes con `alt` y sin duplicados ni omisiones, destino del skip link resuelto. No hay Schema.org inventado.
- [x] **E3. Verificar criterios de aceptación y contrato global.** Home incluye encabezado y footer con contrato documentado, secciones organizadas con columnas responsive, navegación/labels accesibles, contenido de contacto ficticio autorizado y formulario inactivo. No se declaran certificaciones ni pagos aceptados. Catálogo, Producto, Carrito y Checkout quedan pendientes de integrar el patrón en sus funcionalidades; no se modificaron.
- [x] **E4. Actualizar artefactos SDD si cambió el alcance.** `specs.md` y `plan.md` reflejan el estado implementado, la identidad ficticia autorizada, el uso local de Old London y los pendientes de las otras páginas; Home no añadió funcionalidades de tienda.

## Dependencias y límites

- A1 debe completarse antes de comenzar cualquier tarea de implementación.
- A3 y A4 deben estar resueltas antes de fijar estructura de estilos, contenido, imágenes o enlaces.
- B1 y B2 deben definirse antes de implementar navbar/footer en Home.
- Las tareas de esta lista cubren únicamente la funcionalidad Home. La incorporación del contrato global a las otras páginas queda para sus respectivas funcionalidades.
- No realizar commits, cambios de rama ni implementación como parte de la creación o revisión de este documento.
