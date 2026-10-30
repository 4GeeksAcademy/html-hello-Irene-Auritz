# Tareas — Checkout unificado

La petición vigente requiere tres pantallas alternables dentro de `Checkout.html`, con un solo paso visible a la vez. Sustituye tanto la construcción multipágina como las secciones visibles simultáneamente. Los campos siguen siendo opcionales y el recorrido no recoge ni procesa datos.

## 1. Unificar estructura

- [x] Conservar `Checkout.html` como entrada y compartir fuentes/tokens de Home.
- [x] Reunir datos personales, dirección de entrega y pago en paneles alternables con un único título principal y Datos personales como pantalla inicial.
- [x] Mostrar únicamente el panel seleccionado por enlaces internos, usando Tailwind, `:target` y `:has()` sin JavaScript.
- [x] Convertir el índice superior en enlaces a las secciones, sin un paso actual fijo.

## 2. Integrar los controles y la navegación

- [x] Mantener los diez campos de contacto y dirección etiquetados y opcionales.
- [x] Integrar las tres opciones de pago nativas, sin campos bancarios ni envío.
- [x] Añadir enlaces de avance/regreso a destinos internos que puedan recibir foco.
- [x] Mantener dentro de Pago los enlaces al carrito y al catálogo, sin cuarta pantalla.
- [x] Añadir «Confirmar pago» y un diálogo nativo de agradecimiento autorizado, sin procesamiento, con fondo desenfocado y título VHS Gothic.
- [x] Dirigir ambos enlaces de cierre del diálogo a Inicio y evitar el descarte por Escape o clic en el fondo.
- [x] Convertir las rutas antiguas en redirecciones HTML con enlaces de respaldo.

## 3. Revisar el resultado

- [x] Revisar errores del editor tras unificar el contenido.
- [x] Comprobar IDs únicos, etiquetas, destinos internos, tres paneles y reglas de selección con Datos personales por defecto.
- [ ] Comprobar recursos de la página resultante en navegador.
- [ ] Recorrer en navegador las secciones con campos vacíos, teclado y distintos medios seleccionados.
- [ ] Comprobar contraste medido y adaptación visual en móvil, tableta y escritorio.
- [ ] Verificar en navegador compatible la apertura declarativa, el foco, el desenfoque y el regreso a Inicio desde el diálogo.

Las revisiones visuales anteriores seguían pendientes porque se omitieron las herramientas de navegador. No se consideran cubiertas por el control de errores del editor.

La comprobación estructural de la versión con pantallas alternables pasó: tres paneles, reglas de selección, IDs únicos, enlaces internos y 13 controles etiquetados sin obligatoriedad ni envío. No sustituye la comprobación visual, de foco o de recursos en navegador.