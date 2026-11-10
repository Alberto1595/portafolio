# Showcase Automotriz de APX

> Colección de demostraciones con marcas e inventarios ficticios. Documenta experiencia de producto, arquitectura frontend y calidad técnica, sin publicar código fuente ni presentar las demos como clientes reales.

---

## Descripción General

**Showcase Automotriz** reúne tres aplicaciones con objetivos comerciales distintos: descubrimiento de autos nuevos, evaluación de seminuevos premium y búsqueda práctica de vehículos por precio y características.

El valor del proyecto está en resolver diferentes decisiones de compra con experiencias propias, compartiendo contratos de datos e infraestructura de desarrollo sin convertir los sitios en la misma plantilla.

---

## Objetivo del Proyecto

- Demostrar diseño y desarrollo adaptados a segmentos distintos.
- Facilitar descubrimiento, filtrado y evaluación de vehículos.
- Construir páginas de detalle con información útil para la decisión.
- Preparar una arquitectura capaz de incorporar inventario administrado.

---

## Arquitectura

**Stack tecnológico:**

- **Aplicaciones:** Next.js, React, TypeScript y CSS propio por experiencia.
- **Organización:** monorepo con pnpm y Turborepo.
- **Datos:** contratos de dominio y una interfaz de repositorio de inventario.
- **Integración:** adaptador HTTP del catálogo de APX Auto para Vía Clara.
- **Calidad:** Vitest, Playwright, validación TypeScript y auditorías Lighthouse documentadas.

Las aplicaciones comparten tipos y utilidades básicas. La composición visual y las interacciones comerciales se mantienen dentro de cada experiencia.

---

## Módulos y Funcionalidades Clave

### Morrow Motor Company

- Presentación de una marca ficticia de vehículos eléctricos y sus familias de modelos.
- Página del modelo Meridian con selección de versión y especificaciones asociadas.
- Recorrido por diseño, interior, autonomía y carga con datos conceptuales de demostración.
- Acciones de consulta contextualizadas; no constituyen una reserva o prueba de manejo real.

### Archivo Norte

- Catálogo editorial de seminuevos premium con filtros y ordenamiento.
- Ficha completa para una unidad demostrativa Porsche 911.
- Galería con miniaturas, navegación por teclado y vista a pantalla completa.
- Información de configuración, condición y procedencia con alcance ilustrativo explícito.
- Consultas que conservan la identidad de la unidad.

### Vía Clara Seminuevos

- Inventario con filtros por marca, carrocería, precio, año, kilometraje y transmisión.
- Ordenamiento, conteo de resultados, criterios reflejados en URL y recuperación de búsquedas vacías.
- Filtros móviles y rutas rápidas por presupuesto o características.
- Ficha detallada para una unidad demostrativa Nissan Kicks.
- Estimación ilustrativa de mensualidad con supuestos visibles.
- Lectura opcional del catálogo de APX Auto, con validación de respuesta y alternativa de datos demo.

---

## Decisiones Técnicas Clave

- **Diseño por intención de compra:** Morrow prioriza el modelo; Archivo Norte, la unidad y su evaluación; Vía Clara, precio, filtros y datos comparables.
- **Contrato de inventario independiente:** permite cambiar la fuente de datos sin rehacer las páginas.
- **Renderizado en servidor e interacción acotada:** limita JavaScript de cliente a filtros, galerías y navegación.
- **Accesibilidad y rendimiento:** imágenes optimizadas, fuentes locales, controles de teclado y movimiento reducido.
- **Detalle solo cuando existe:** evita enlaces a fichas incompletas o flujos de contacto que aparenten operaciones inexistentes.

---

## Mi Rol en el Proyecto

- Definición de las tres experiencias y su arquitectura de información.
- Desarrollo de identidades visuales y aplicaciones responsive.
- Modelado de vehículos y contrato de acceso a inventario.
- Implementación de filtros, galerías y páginas de detalle.
- Integración del catálogo administrado de APX Auto con Vía Clara.
- Optimización de imágenes, fuentes, metadata y accesibilidad.
- Preparación de pruebas y documentación de calidad y publicación.

---

## Resultados

- Tres experiencias diferenciadas sobre una base técnica compartida.
- Recorridos funcionales de búsqueda y evaluación con inventario demostrativo.
- Arquitectura preparada para sustituir datos locales por un servicio de catálogo.
- Auditorías locales documentadas en seis rutas: rendimiento móvil final entre 91 y 95, y 100 en accesibilidad, buenas prácticas y SEO; escritorio con 100 en las cuatro categorías.

Las cifras corresponden a auditorías de laboratorio registradas en la documentación, no a una medición nueva de esta actualización ni a datos de usuarios reales. Las consultas, cotizaciones y mensualidades ilustrativas no equivalen a CRM, financiamiento o reservas comerciales conectadas.

---

## Estado

Demos implementadas / Evolución de catálogo e integraciones.
