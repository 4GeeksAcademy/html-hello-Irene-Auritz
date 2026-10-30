# 📄 Contexto del Proyecto: Prototipo E-Commerce de Streetwear de Lujo

---

## 1. Visión General e Identidad del Cliente
* **Cliente:** Marca de ropa de *Luxury Streetwear* (alta gama / moda urbana de lujo) con sede en París, Francia.
* **Idioma de desarrollo y contenidos:** Español.
* **Objetivo del Proyecto:** Crear un prototipo web visual y funcional para su próxima tienda en línea. Debe transmitir una estética moderna, exclusiva, elegante y minimalista.
* **Rol del Equipo:** Celda de desarrollo en consultora tecnológica trabajando bajo metodología ágil (Gitflow / Pull Requests).

---

## 2. Requisitos Técnicos y Alcance
* **Tech Stack Permitido:** 
  * HTML5 Semántico
  * Tailwind CSS (vía CDN o CLI, sin componentes/frameworks JS externos ni librerías pesadas)
  * Schema.org (JSON-LD o Microdatos)
* **Filosofía de Arquitectura:** Prototipo estático multipágina (MPA) ligero, enfocado en rendimiento, accesible y 100% responsivo (Mobile First / Tablet / Desktop).
* **Rendimiento:** Puntuación objetivo en **PageSpeed Insights ≥ 80 pts** (idealmente > 90 pts).

---

## 3. Estructura de Vistas a Implementar (5 Páginas HTML)

### 🧩 Componentes Transversales (Globales)
1. **Navbar (Superior / Fijo):**
   * Logo de la marca (Streetwear de lujo)
   * Barra de búsqueda
   * Menú de cuenta de usuario / Acceso
   * Reutilizado y consistente en todas las vistas.
2. **Footer (Inferior):**
   * **Categorías:** Calzado, Camisas/Camisetas, Pantalones, Accesorios.
   * **Legal:** Términos y condiciones, Política de privacidad, Sobre la marca.
   * **Contacto:** Datos de contacto / Redes.
   * Reutilizado y consistente en todas las vistas.

---

### 📄 Detalle por Página

#### 1. Home (`index.html`)
* **Navbar & Footer**
* **Hero Section:** Destacado visual impactante (campaña de lanzamiento o prendas insignia).
* **Sección 1:** Listado horizontal (Cards) con *Nuevos Lanzamientos*.
* **Sección 2:** Listado horizontal (Cards) con *Más Vendidos*.
* **SEO/Schema:** Implementación de `Organization` y `WebSite`.

#### 2. Catálogo (`catalogo.html`)
* **Navbar & Footer**
* **Barra de Filtros:**
  * Filtro por Categoría
  * Filtro por Talla
* **Grid de Productos:** Rejilla responsiva $4 \times 5$ (20 productos visibles de referencia).

#### 3. Vista de Producto (`producto.html`)
* **Navbar & Footer**
* **Layout 2 Columnas (Desktop):**
  * *Columna Izquierda:* Galería/Imagen principal del producto (~50% ancho).
  * *Columna Derecha:* Información clave (Nombre, Código/Referencia, Selector de Talla, Precio, Selector de Cantidad, Botón "Agregar al carrito").
* **Sección Inferior:** Descripción detallada del producto (Materiales de alta gama, Uso recomendado / Escenarios).
* **SEO/Schema:** Implementación de `Product` y `Offer`.

#### 4. Carrito de Compras (`carrito.html`)
* **Navbar & Footer**
* **Vista Completa de Página** (no modal/panel lateral):
  * Listado de productos (al menos 3 productos de ejemplo prémium cargados).
  * Detalle por fila: Miniatura, Precio unitario, Cantidad, Subtotal por producto.
* **Cuadro de Totalización / Resumen:**
  * Subtotal, Impuestos (IVA), Total general.
  * Botón destacado "Comprar" (Redirige a Checkout).

#### 5. Formulario de Pago / Checkout (`checkout.html`)
* **Navbar & Footer**
* **Flujo en 3 Pasos Visuales:**
  1. *Paso 1:* Datos Personales.
  2. *Paso 2:* Dirección de Entrega.
  3. *Paso 3:* Datos de Pago con Tarjeta.

---

## 4. Guía de Calidad y Criterios de Aceptación

### 🎯 Criterios de Evaluación
| Criterio | Requisito de Cumplimiento |
| :--- | :--- |
| **HTML Semántico** | Uso correcto de `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`, `<form>`. |
| **Tailwind CSS** | Clases utility coherentes, diseño limpio sin estilos inline innecesarios ni CSS sobrante. |
| **Responsividad** | Total adaptabilidad sin desbordamientos (*scroll* horizontal) ni layouts rotos en móviles. |
| **Schema.org** | Marcado estructurado correcto en Home y Ficha de Producto. |
| **Rendimiento** | Código limpio, imágenes optimizadas y livianas para garantizar la nota en PageSpeed. |

---

## 5. Metodología de Trabajo y Git Workflow

### 🌲 Reglas de Ramas y Commits
* **Prohibido commit directo a `main`**.
* **Nomenclatura de ramas:** `feature/nombre-vista` (ej. `feature/home`, `feature/catalogo`, `feature/producto`, `feature/carrito`, `feature/checkout`).
* **Pull Requests (PR):**
  * Toda característica requiere su propia PR hacia `main`.
  * La PR debe llevar una descripción clara de lo implementado.
  * Antes de subir una PR o fusionar, actualizar con `main` (`git pull origin main`).
* **Commits Semánticos e Incrementales:**
  * Ejemplos: `feat: add navbar and hero to home page`, `style: fix product grid layout on mobile`.