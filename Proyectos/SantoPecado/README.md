# Santo Pecado

> Caso de estudio de una página real para un restaurante. Se documentan la solución, sus funcionalidades y mi participación, sin incorporar código fuente al portafolio.

---

## Descripción General

**Santo Pecado** es un menú digital interactivo para un restaurante de Cadereyta Jiménez. Permite consultar productos y precios, elegir variantes, formar un carrito y preparar un pedido para enviarlo al WhatsApp del negocio.

El valor del proyecto está en transformar una carta informativa en una herramienta de pedido: el cliente selecciona antes de conversar y el restaurante recibe un resumen con productos, cantidades, variantes, importe y modalidad de entrega.

---

## Objetivo del Proyecto

- Facilitar la consulta del menú desde el teléfono.
- Mostrar precios y presentaciones antes de iniciar el pedido.
- Reducir la captura manual del resumen dentro del chat.
- Integrar la experiencia digital con el canal de atención existente del restaurante.

---

## Arquitectura

**Stack tecnológico:**

- **Frontend:** Next.js, React, TypeScript y Tailwind CSS.
- **Carrito:** Context API y useReducer, con estado en memoria durante la visita.
- **Catálogo:** configuración centralizada del negocio, categorías, productos y variantes.
- **Contacto:** enlace de WhatsApp con mensaje prellenado; redes sociales y Maps.

El cálculo y la preparación del pedido ocurren en el navegador. WhatsApp funciona como entrega del resumen al restaurante; el cliente envía el mensaje y el negocio continúa la atención y confirmación.

---

## Módulos y Funcionalidades Clave

### Menú Digital

- Navegación por categorías de hamburguesas, complementos, carne asada y extras.
- Descripción, precio e identificación de productos destacados.
- Selección de variantes con precio propio, como presentaciones con o sin acompañamiento.
- Información de ubicación, horario y accesos a redes y mapa.

### Carrito de Pedido

- Botón flotante con cantidad de productos e importe acumulado.
- Panel lateral para revisar y ajustar cantidades.
- Identificación independiente de las variantes de un mismo producto.
- Actualización de subtotales y total; opción para vaciar el carrito.

### Entrega y WhatsApp

- Elección entre recoger el pedido o recibirlo a domicilio.
- Captura de dirección para entrega.
- Inclusión del costo de envío configurado cuando corresponde.
- Generación de un mensaje con el pedido completo y su modalidad.

---

## Decisiones Técnicas Clave

- **WhatsApp como canal comercial:** aprovecha una herramienta que el restaurante ya utiliza para atender pedidos.
- **Catálogo centralizado:** permite mantener productos, precios y datos del negocio sin dispersarlos entre componentes.
- **Carrito por producto y variante:** evita mezclar presentaciones con precios diferentes.
- **Flujo por pasos:** primero se revisa el carrito y después se define cómo recibirlo.

---

## Retos Técnicos

- Mantener coherencia entre el precio mostrado, la variante elegida y el resumen enviado.
- Conservar un carrito accesible durante la navegación entre categorías.
- Adaptar la identidad visual del restaurante a una interfaz legible en móvil.
- Distinguir el armado del pedido de su aceptación por el negocio.

---

## Mi Rol en el Proyecto

- Desarrollo del menú web y adaptación de la identidad visual.
- Modelado de categorías, productos, precios y variantes.
- Implementación del estado y las operaciones del carrito.
- Desarrollo del flujo de recolección y entrega a domicilio.
- Cálculo del resumen y construcción del mensaje de WhatsApp.
- Integración de ubicación, horarios y redes sociales.
- Mantenimiento y actualización del catálogo del restaurante.

---

## Resultados

- Página real con una carta navegable y un recorrido de pedido completo hasta WhatsApp.
- Información del pedido organizada antes de que comience la atención en el chat.
- Precios, variantes y costo de envío visibles durante la selección.
- Base reutilizable para otros negocios con necesidades similares.

La confirmación del pedido y el cobro se atienden por el negocio; la página no incorpora una pasarela de pago ni un sistema de cocina.

---

## Estado

Página real para restaurante / Mantenimiento del menú y experiencia de pedido.
