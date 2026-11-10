# Patio 11 — Menú Web y Pedidos por WhatsApp

> Demo comercial no oficial de APX. Se documenta el desarrollo de la experiencia y su integración de prueba; no representa un sistema contratado o productivo del restaurante.

---

## Descripción General

**Patio 11** es una demo de sitio de restaurante y menú interactivo que conecta la selección de productos en web con una conversación de WhatsApp. La persona personaliza su pedido en una interfaz visual y el backend reconstruye el resumen para responder con un folio y datos de transferencia simulados.

Su valor está en resolver la complejidad de una carta extensa: las categorías, opciones y extras se eligen en la web, mientras WhatsApp conserva la continuidad de la atención.

---

## Objetivo del Proyecto

- Hacer navegable una carta con categorías y preparaciones diferentes.
- Permitir personalización de productos sin depender de mensajes libres.
- Mantener carritos independientes por sucursal.
- Integrar el pedido web con un flujo conversacional verificable.

---

## Arquitectura

**Stack tecnológico:**

- **Web:** HTML, CSS y JavaScript con módulos de catálogo, carrito y protocolo de checkout.
- **Persistencia local:** localStorage, separado por tienda.
- **Backend de demo:** módulos Node.js en el entorno Next.js/Vercel de APX.
- **Mensajería:** transporte compartido con la demo dental y conversaciones persistidas en PostgreSQL.
- **Calidad:** pruebas del modelo de carrito y de integración conversacional con PGlite.

El enlace de WhatsApp incluye un resumen legible y una referencia estructurada. El backend valida los datos y recalcula desde su catálogo; no toma el importe escrito por el cliente como fuente de verdad.

---

## Módulos y Funcionalidades Clave

### Sitio y Menú

- Portada comercial y entrada al menú.
- Selector de tienda, categorías y búsqueda.
- Detalle de producto con variantes, ingredientes removibles, extras, combos y notas.
- Validación de elecciones obligatorias antes de agregar.

### Carrito

- Carrito flotante con edición de preparaciones y cantidades.
- Separación de líneas cuando cambian opciones o instrucciones.
- Persistencia por sucursal y restauración con precios recalculados desde catálogo.
- Modalidad de pedido y notas generales.

### Continuidad en WhatsApp

- Mensaje prellenado con resumen y referencia de checkout.
- Reconocimiento del pedido y selección de demo restaurante en el backend.
- Validación de catálogo, opciones, cantidades y vigencia de la referencia.
- Respuesta con folio, resumen y ficha de transferencia simulada.
- Consulta de estado, cancelación y simulación de comprobante dentro de la sesión.

---

## Decisiones Técnicas Clave

- **Selección visual y conversación conectadas:** cada canal resuelve la parte del recorrido que le resulta más clara al usuario.
- **Precios en centavos enteros:** mantiene consistencia al calcular cantidades, extras y combos.
- **Referencia estructurada validada:** permite reconstruir el pedido sin interpretar el texto humano como una orden confiable.
- **Identidad de checkout:** repetir el mismo resumen conserva su referencia; cambiarlo obliga a generar una nueva.
- **Reglas compartidas:** catálogo y cálculo se mantienen alineados entre la web y el backend.

---

## Retos Técnicos

- Conservar variantes e instrucciones al editar un producto.
- Restaurar el carrito sin confiar en precios antiguos guardados en el navegador.
- Mantener aislamiento entre sucursales, usuarios y demos.
- Respetar límites de longitud del mensaje sin truncar el pedido.

---

## Mi Rol en el Proyecto

- Diseño del recorrido comercial y estructura del sitio.
- Implementación del menú, personalización y carrito.
- Modelado del catálogo, modificadores y reglas de precio.
- Desarrollo del protocolo web–WhatsApp y validación del lado servidor.
- Integración con el motor conversacional compartido.
- Preparación de pruebas de cálculo, persistencia, repetición de mensajes y recuperación.
- Publicación y documentación de la demo.

---

## Resultados

- Demo que conserva el contexto del pedido entre web y WhatsApp.
- Personalización y cálculos consistentes entre preparaciones.
- Flujo de prueba con folio y respuesta de transferencia claramente simulada.
- Pruebas documentadas de carrito y de integración con la sesión persistente.

No procesa pagos ni concilia depósitos. El pedido vive en la sesión de demostración: una operación real requeriría órdenes durables, aceptación de cocina, cobertura y costos de entrega confirmados.

---

## Estado

Demo implementada / Validación comercial. No es un sistema de pedidos productivo de Patio 11.
