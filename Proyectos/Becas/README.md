# Sistema de Becas Cadereyta 2026

> ⚠️ El código fuente de este proyecto es privado debido a confidencialidad institucional.  
> Este documento describe la funcionalidad, arquitectura y decisiones técnicas del sistema.

---

## Descripción General
**Sistema de Becas Cadereyta 2026** es una plataforma web desarrollada para la **gestión integral del programa de becas municipales de Cadereyta Jiménez**, digitalizando el proceso completo desde el registro de solicitantes hasta la resolución y notificación de resultados.

El sistema centraliza la recepción de solicitudes, validación de documentos, revisión administrativa y comunicación con los solicitantes mediante notificaciones automáticas por correo electrónico.

---

## Objetivo del Proyecto
- Digitalizar el proceso de solicitud y gestión de becas municipales
- Centralizar la revisión y resolución de solicitudes en un panel administrativo
- Automatizar notificaciones a solicitantes en cada etapa del proceso
- Garantizar trazabilidad y control del programa de becas
- Facilitar la carga masiva de registros para operación a escala

---

## Arquitectura

**Stack tecnológico:**

- **Frontend / BFF:** Next.js (App Router) + TypeScript + React + Tailwind CSS
- **Backend:** Azure Functions (Python)
- **Base de datos:** Azure SQL Database
- **Almacenamiento:** Azure Blob Storage (documentos y comprobantes)
- **Notificaciones:** Email automatizado por eventos
- **Infraestructura:** Microsoft Azure

Arquitectura serverless con Next.js como capa BFF, consumiendo Azure Functions como backend desacoplado y Azure SQL como fuente de verdad.

---

## Seguridad
- Autenticación con **JWT en cookies HttpOnly**
- **Control de acceso por rol** — solicitantes y administradores
- Middleware de protección de rutas privadas
- Almacenamiento de documentos con **SAS tokens** de alcance y vigencia limitada
- Manejo seguro de credenciales mediante variables de entorno
- Sin exposición de información sensible entre solicitantes

---

## Módulos y Funcionalidades Clave

### Portal de Registro
- Formulario de solicitud de beca por etapas
- Carga de documentos y comprobantes a Azure Blob Storage
- Confirmación de registro con notificación automática por email

### Panel Administrativo
- Visualización de todas las solicitudes con filtros por estatus
- Acciones por solicitud: **Aceptar, Rechazar, Verificar**
- Revisión de documentos adjuntos por solicitante
- Carga masiva de registros mediante archivo

### Notificaciones Automáticas
- Confirmación de recepción de solicitud
- Notificación de cambio de estatus (aceptado, rechazado, en verificación)
- Comunicación directa con el solicitante sin intervención manual

### Gestión Documental
- Almacenamiento de comprobantes y documentos en Azure Blob Storage
- Acceso seguro mediante SAS tokens con vigencia limitada
- Organización por solicitante y tipo de documento

---

## Decisiones Técnicas Clave
- **Arquitectura serverless (Azure Functions):** escala automáticamente para absorber el volumen de solicitudes en períodos de alta demanda sin infraestructura dedicada.
- **Next.js como BFF:** centraliza autenticación y control de acceso hacia el backend, evitando exposición directa de endpoints.
- **Azure Blob con SAS tokens:** permite acceso seguro a documentos sensibles sin exponer credenciales ni rutas permanentes.
- **Notificaciones por eventos:** reduce carga operativa del equipo administrativo automatizando la comunicación en cada cambio de estatus.
- **Carga masiva:** facilita la operación a escala sin captura manual registro por registro.

---

## Retos Técnicos
- Manejo seguro de documentos e información personal de solicitantes
- Automatización de notificaciones por múltiples eventos del flujo
- Diseño de flujo administrativo claro para personal no técnico
- Escalabilidad para absorber picos de solicitudes al inicio del programa
- Validación robusta de documentos en carga masiva

---

## Mi Rol en el Proyecto
- Diseño completo de la arquitectura del sistema
- Desarrollo del frontend en Next.js
- Implementación del backend en Azure Functions (Python)
- Modelado y administración de base de datos en Azure SQL
- Integración de almacenamiento documental en Azure Blob Storage
- Implementación de notificaciones automáticas por email
- Desarrollo del panel administrativo y flujo de resolución de solicitudes
- Diseño e implementación de carga masiva de registros

---

## Resultados Esperados
- Atención a **~200 solicitantes** en el programa de becas 2026
- Eliminación del proceso manual de registro y notificación
- Trazabilidad completa del estado de cada solicitud
- Reducción de tiempos administrativos mediante automatización

---

## Estado
Desarrollo completado — pendiente de despliegue y operación
