# Brasa Norte

> Restaurante ficticio utilizado como demostración de APX. Este caso describe una experiencia desarrollada para mostrar un menú y preparar pedidos por WhatsApp; no representa un cliente real.

---

## Descripción General

**Brasa Norte** es una aplicación web de restaurante con catálogo, variantes, carrito y entrega del resumen a WhatsApp. Forma parte del mismo monorepo del showcase automotriz, pero conserva su propio contenido, diseño y reglas de producto.

Su valor es demostrar una solución comercial enfocada: que el visitante encuentre qué pedir, revise el importe y lleve a la conversación un resumen ordenado, con los datos necesarios para continuar la atención.

---

## Objetivo del Proyecto

- Presentar productos y precios en una experiencia visual adaptable.
- Permitir selección de variantes y edición del carrito.
- Recopilar los datos del pedido según su modalidad.
- Generar un mensaje de WhatsApp que conserve el contexto de la selección.

---

## Arquitectura

**Stack tecnológico:**

- **Aplicación:** Next.js, React y TypeScript.
- **Organización:** aplicación independiente dentro de un monorepo pnpm.
- **Datos:** catálogo local y reglas de pedido tipadas.
- **Recursos:** imágenes ilustrativas generadas para la demo y optimizadas en WebP.
- **Calidad:** pruebas unitarias y recorridos Playwright documentados.

El carrito conserva sus datos en memoria durante la visita. La aplicación no necesita una base de datos ni un backend de pedidos para preparar el mensaje.

---

## Módulos y Funcionalidades Clave

- Navegación por categorías y búsqueda de productos.
- Presentación de imágenes, variantes y precios.
- Carrito con edición de cantidades, eliminación y límite por línea.
- Captura de nombre, notas opcionales y dirección para entrega a domicilio.
- Validación de campos requeridos.
- Construcción de un mensaje de WhatsApp con el resumen del pedido.
- Recursos alternativos identificados cuando falta una fotografía.

---

## Decisiones Técnicas Clave

- **Aplicación autónoma:** comparte herramientas de desarrollo sin depender del dominio de vehículos de otras apps del monorepo.
- **Cálculo desde la variante seleccionada:** mantiene consistencia entre catálogo, carrito y mensaje.
- **Estado en memoria:** suficiente para el alcance de demostración; el carrito se reinicia al recargar.
- **Imágenes propias de demo:** permiten explorar la propuesta visual sin reutilizar recursos de restaurantes reales.

---

## Retos Técnicos

- Conservar el resumen correcto al cambiar variantes o cantidades.
- Distinguir los campos requeridos para recoger y recibir a domicilio.
- Hacer usable el carrito en móvil y con teclado.
- Integrar una nueva aplicación en el monorepo conservando independencia de producto.

---

## Mi Rol en el Proyecto

- Desarrollo de la propuesta de restaurante y su experiencia web.
- Implementación de catálogo, búsqueda y navegación por categorías.
- Desarrollo de carrito, validación y cálculo de pedidos.
- Integración del mensaje contextual de WhatsApp.
- Preparación y optimización de recursos visuales.
- Integración en la estructura de desarrollo y pruebas del monorepo.

---

## Resultados

- Demo funcional del recorrido menú–carrito–WhatsApp.
- Reglas documentadas y pruebas de precios, variantes, cantidades y campos requeridos.
- Recorridos de navegador documentados para búsqueda, edición, teclado y tamaños de 320 a 1920 píxeles.

WhatsApp abre un mensaje preparado que el visitante debe enviar. La página no acepta el pedido en nombre de una cocina, cobra pagos ni confirma cobertura de reparto.

---

## Estado

Demo implementada / Restaurante y contenido ficticios.
