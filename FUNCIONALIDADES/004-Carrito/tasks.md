# Tareas de implementación — Carrito

- **Funcionalidad:** `004-Carrito`
- **Estado:** tarjetas de producto implementadas; validación final pendiente
- **Especificación:** [`specs.md`](./specs.md)
- **Plan:** [`plan.md`](./plan.md)
- **Rama comprobada al crear esta lista:** `Carrito`

## Reglas de ejecución

- Completar las tareas en el orden indicado. No comenzar una tarea siguiente hasta terminar y marcar la actual.
- Marcar cada checkbox únicamente cuando el resultado de esa tarea esté terminado y comprobado.
- Antes de implementar, validar que la especificación, el plan y esta lista están aprobados y que la rama activa sigue siendo `Carrito` o `feature/carrito`.
- No cambiar de rama silenciosamente, no hacer commits como parte de esta secuencia y no ampliar el alcance a otras páginas.
- Si una decisión o una discrepancia bloquea la tarea, detenerse en ella, documentar el bloqueo y no marcarla completa.

## A. Preparación

- [x] **A1. Confirmar alcance y artefactos SDD.** Revisar `specs.md`, `plan.md`, `tasks.md` y el placeholder actual; confirmar que el alcance sigue siendo una cesta estática de tres artículos con importes ficticios. Resolver cualquier contradicción antes de editar código. El inicio de implementación solicitado por el usuario confirma la aprobación de estos artefactos y su alcance actual.
- [x] **A2. Verificar rama y dependencias locales.** Confirmar la rama permitida; revisar destinos de Home, Catálogo y Checkout, archivos de imagen y hoja CSS compartida. Calcular las rutas relativas desde `FUNCIONALIDADES/004-Carrito/` y confirmar que no se usará el CDN del placeholder. Rama actual `Carrito`; existen las páginas destino y recursos locales requeridos; no se encontró Tailwind local, por lo que se reutilizará el CSS local compartido de Home y una hoja propia de Carrito.

## B. Estructura y contenido HTML

- [x] **B1. Crear el documento HTML de Carrito.** Reemplazar el placeholder por una estructura HTML5 completa en español, con título y descripción únicos, enlace de salto al contenido y un H1; conservar únicamente recursos locales. Queda enlazado el CSS local compartido y el archivo CSS específico previsto.
- [x] **B2. Integrar navegación compartida.** Replicar el navbar de Home con rutas relativas verificadas, marcar Carrito como actual y mantener los mismos nombres accesibles y orden visual.
- [x] **B3. Maquetar los tres artículos de referencia.** Presentar CHAQUETA.jpg, SHIRT.jpg y WING.jpg con alternativas contextuales, nombres, variantes, cantidades, precio unitario TTC y subtotal por línea; no incluir controles de edición o eliminación.
- [x] **B4. Añadir resumen y enlaces de navegación.** Mostrar subtotal sin IVA, IVA incluido al 20 % y total TTC con los importes establecidos; enlazar de forma clara a Checkout y Catálogo sin simular procesamiento de compra.
- [x] **B5. Integrar el footer compartido.** Replicar el footer de Home y verificar/ajustar todos sus destinos a rutas relativas desde Carrito, conservando la estructura y accesibilidad comunes.

## C. Estilos y adaptación

- [x] **C1. Enlazar los estilos compartidos y definir los específicos necesarios.** Cargar localmente la hoja de Home con la ruta correcta; añadir solo las reglas propias de Carrito que no alteren ni requieran modificar páginas vecinas. No añadir CDN ni recursos remotos. Se creó `styles.css` dentro de la funcionalidad y se enlazó localmente junto al CSS compartido.
- [x] **C2. Componer el resumen y las líneas para distintos tamaños.** Ajustar el orden y agrupación de producto, variante, cantidad e importes para móvil, tableta y escritorio; conservar legibilidad y evitar scroll horizontal sin forzar una rejilla de catálogo. La hoja específica apila las líneas en móvil y presenta las columnas de producto/precios y el resumen lateral en pantallas amplias.
- [x] **C3. Revisar coherencia visual y accesibilidad.** Aplicar paleta, tipografía y espaciado comunes; comprobar contraste, foco visible, orden de lectura, enlaces por teclado y legibilidad de importes. Mantener fuentes ornamentales fuera de lectura y precios. La página reutiliza los tokens globales, reserva Old London para el título, usa VHS Gothic solo en encabezados breves y define foco destacado; la medición de contraste queda pendiente de validación final.

## D. Validación y cierre

- [x] **D1. Validar HTML y navegación local.** Comprobar estructura, `lang="es"`, un H1, IDs únicos, destino del skip link, imágenes, CSS y enlaces a Catálogo, Checkout y footer. La revisión del HTML, diagnóstico del editor y resolución de destinos locales no reportaron errores.
- [x] **D2. Verificar datos, alternativas y alcance estático.** Confirmar tres artículos, texto alternativo contextual y coherencia aritmética: 900 € + 180 € + 300 € = 1.380 € TTC; 1.150 € netos + 230 € de IVA incluido = 1.380 €. Confirmar ausencia de envío añadido, JavaScript, CDN, controles simulados y afirmaciones comerciales no autorizadas. Los importes coinciden con `specs.md`; se conserva únicamente el formulario de contacto compartido de Home en estado deshabilitado, no hay controles de carrito ni pedido.
- [ ] **D3. Revisar presentación responsive y teclado.** Comprobar tamaños móvil, tableta y escritorio con herramientas disponibles, ausencia de desbordamiento, foco perceptible y contraste. No afirmar inspección visual en navegador si no se realizó. La hoja define composición mobile-first y breakpoints en 42rem y 72rem, y se han añadido estilos de foco; queda pendiente una comprobación renderizada en navegador, no disponible en esta sesión.
- [ ] **D4. Ejecutar verificaciones finales y actualizar SDD.** Ejecutar `git diff --check` y validaciones disponibles; registrar solo resultados comprobados en `specs.md` y cambiar el estado de esta lista cuando la implementación esté realmente finalizada. Se actualizaron plan y especificación con el estado real, pero la verificación `git diff --check` no llegó a ejecutarse.

## E. Referencias a Producto

- [x] **E1. Convertir las prendas en tarjetas enlazadas.** Cada artículo se presenta como tarjeta visual con imagen y nombre enlazados a `../003-Vista-producto/Producto.html`, enlace explícito «Ver producto» e identificador semántico estable (`data-product-ref`). `Producto.html` sigue siendo un placeholder sin tarjetas ni IDs de producto; por ello no se inventan fragmentos destino inexistentes. Cuando se construyan esas tarjetas, deberán usar las mismas claves (`chaqueta-piel-bordada`, `camiseta-grafica-manga-larga`, `vaqueros-grafico-alas`) y Carrito podrá enlazar a sus anclas concretas.
