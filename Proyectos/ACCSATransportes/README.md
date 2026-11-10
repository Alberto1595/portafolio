# ACCSA Transportes

> Caso de estudio de un sitio comercial real. Este documento presenta el trabajo realizado, su valor para el negocio y la arquitectura general, sin incorporar código fuente ni configuraciones privadas.

---

## Descripción General

**ACCSA Transportes** es un sitio web comercial para una empresa de suministro y transporte de agua en Nuevo León. La solución permite conocer los servicios, identificar el tipo de agua requerido y solicitar una cotización desde el sitio o por WhatsApp.

El proyecto combina desarrollo web, organización de contenido comercial e integración de un formulario con servicios en Azure. Su valor está en convertir la presencia digital de la empresa en un canal de consulta y captación de solicitudes.

---

## Objetivo del Proyecto

- Presentar los servicios de la empresa con información clara para clientes particulares e industriales.
- Facilitar consultas por tipo de agua, volumen y zona de entrega.
- Ofrecer vías directas de contacto por WhatsApp, llamada y formulario.
- Construir una base de SEO local orientada a búsquedas de pipas de agua en Monterrey y Nuevo León.

---

## Arquitectura

**Stack tecnológico:**

- **Frontend:** Next.js, React, TypeScript y Tailwind CSS.
- **Integración de cotizaciones:** consumo de un endpoint de Azure Functions mediante HTTP.
- **Contacto:** enlaces a WhatsApp y llamada telefónica.
- **SEO:** metadata por página, URLs canónicas, datos estructurados JSON-LD y generación de sitemap y robots.txt.

El sitio presenta el contenido comercial y envía los datos del formulario al servicio de cotización. La atención, disponibilidad y cierre de la contratación corresponden al equipo de la empresa.

---

## Módulos y Funcionalidades Clave

### Presentación de Servicios

- Páginas específicas para agua de pozo, por ósmosis, desmineralizada y residual tratada.
- Explicación de aplicaciones, cobertura y preguntas frecuentes.
- Presentación de capacidades de transporte de 10,000 a 50,000 litros.
- Galería, información de la empresa y navegación compartida entre servicios.

### Solicitud de Cotización

- Captura de nombre, teléfono, tipo de agua, volumen aproximado y zona de entrega.
- Envío al backend mediante una petición HTTP.
- Estados de envío, confirmación y error para orientar al visitante.
- Accesos alternativos por WhatsApp y teléfono.

### Visibilidad en Buscadores

- Títulos y descripciones enfocados en cada servicio.
- Contenido geográfico para búsquedas locales.
- Datos estructurados de negocio y servicios; preguntas frecuentes en la página de agua de pozo.
- Enlaces internos entre portada, servicios y cotización.

---

## Decisiones Técnicas Clave

- **Una página por servicio:** permite explicar necesidades distintas y ofrecer destinos específicos para búsquedas orgánicas.
- **Formulario conectado a Azure:** separa la presentación comercial del procesamiento de la solicitud.
- **Contacto en varios puntos del recorrido:** facilita pasar de una consulta informativa a una conversación con la empresa.
- **Componentes compartidos:** mantiene consistencia entre páginas y simplifica la evolución del contenido.

---

## Retos Técnicos

- Organizar servicios similares sin perder la diferencia entre sus aplicaciones.
- Dar prioridad al tipo de agua, volumen y ubicación que necesita conocer el equipo comercial.
- Mantener navegación y llamadas a la acción claras en dispositivos móviles.
- Mejorar contenido y SEO sin confundir información comercial con disponibilidad confirmada.

---

## Mi Rol en el Proyecto

- Desarrollo de la aplicación web y sus páginas de servicio.
- Organización del contenido y del recorrido de solicitud de cotización.
- Integración del formulario con Azure Functions.
- Implementación de contacto por WhatsApp y teléfono.
- Configuración de metadata, datos estructurados y sitemap.
- Mantenimiento y mejora de la portada y navegación comercial.

---

## Resultados

- Sitio real que concentra información de servicios y canales de contacto.
- Solicitudes estructuradas con los datos iniciales necesarios para cotizar.
- Páginas específicas para consultas por servicio y ubicación.
- Base técnica para continuar trabajando la visibilidad orgánica y evaluar resultados con datos de búsqueda.

Estos resultados describen capacidades entregadas; no atribuyen incrementos de ventas o posicionamiento sin una medición comparativa.

---

## Estado

Sitio comercial real / Mantenimiento y mejora continua.

[Visitar ACCSA Transportes](https://accsatransportes.com)
