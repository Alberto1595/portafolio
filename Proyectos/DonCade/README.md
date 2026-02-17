# DonCade

> ⚠️ El código fuente de este proyecto es privado debido a confidencialidad institucional.  
> Este documento describe la arquitectura, decisiones técnicas y resultados del sistema.

---

## Descripción General
DonCade es una plataforma digital orientada a la **gestión de reportes ciudadanos y servicios municipales**, diseñada para centralizar solicitudes, automatizar procesos y mejorar la atención a la ciudadanía mediante canales digitales.

El sistema integra mensajería, formularios web, almacenamiento de documentos y generación automatizada de reportes.

---

## Objetivo del Proyecto
- Centralizar reportes ciudadanos en un solo sistema
- Automatizar la recepción, clasificación y seguimiento de solicitudes
- Reducir tiempos de atención y errores manuales
- Facilitar la generación de reportes y documentos oficiales

---

## Arquitectura

**Stack tecnológico:**

- **Backend:** Azure Functions (Python)
- **Base de datos:** Azure SQL Database
- **Almacenamiento:** Azure Blob Storage
- **Frontend:** Next.js
- **Mensajería:** WhatsApp (Twilio)
- **Cache / Estado:** Redis (Azure Cache for Redis)
- **Infraestructura:** Microsoft Azure

Arquitectura orientada a servicios, con funciones desacopladas y manejo de estado conversacional.

---

## Seguridad
- Separación de responsabilidades por servicio
- Manejo seguro de credenciales mediante variables de entorno
- Control de acceso por rol en módulos administrativos
- Uso de almacenamiento seguro para archivos y documentos
- Diseño enfocado en minimizar exposición de datos sensibles

---

## Funcionalidades Clave
- Recepción de reportes ciudadanos vía WhatsApp
- Formularios web para captura estructurada de información
- Manejo de estado conversacional por usuario
- Almacenamiento y gestión de archivos (PDF, imágenes)
- Generación automática de documentos y reportes
- Panel administrativo para revisión y seguimiento
- Exportación de información para análisis y control

---

##  Retos Técnicos
- Manejo de múltiples usuarios concurrentes en mensajería
- Persistencia y recuperación de estados conversacionales
- Optimización de consultas en Azure SQL
- Gestión eficiente de archivos en Blob Storage
- Balance entre automatización y control administrativo
- Seguridad y privacidad de la información ciudadana

---

## Mi Rol en el Proyecto
- Diseño de la arquitectura general del sistema
- Desarrollo completo del backend en Azure Functions
- Modelado y administración de base de datos en Azure SQL
- Integración con WhatsApp mediante Twilio
- Implementación de almacenamiento en Azure Blob Storage
- Automatización de flujos y generación de documentos
- Soporte técnico y evolución del sistema
- Capacitacion de personal

---

## Resultados
- Centralización de reportes ciudadanos
- Reducción de procesos manuales
- Mejora en tiempos de respuesta
- Sistema escalable y mantenible
- Base sólida para ampliación de servicios municipales

---

## Evidencia Visual
Screenshots y diagramas anonimizados disponibles en la carpeta `/assets`.

---

## 📝 Estado
En operación / Evolución continua
