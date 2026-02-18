# Oficialía Mayor

> ⚠️ El código fuente de este proyecto es privado debido a confidencialidad institucional.  
> Este documento describe la funcionalidad, arquitectura y decisiones técnicas del sistema.

---

## Descripción General
**Oficialía Mayor** es una plataforma web administrativa orientada a la **digitalización de trámites internos y atención ciudadana**, centralizando módulos operativos clave bajo un sistema seguro de autenticación y control de sesiones.

La solución permite a personal autorizado gestionar reportes ciudadanos, padrón de jueces auxiliares y trámites de cartillas militares desde un panel web unificado.

---

## Objetivo del Proyecto
- Digitalizar procesos administrativos municipales
- Reducir tiempos operativos y errores manuales
- Centralizar la información ciudadana en módulos especializados
- Proveer validación pública segura mediante QR
- Mejorar trazabilidad y control interno de trámites

---

## Arquitectura

**Stack tecnológico:**

- **Frontend / BFF:** Next.js (App Router) + TypeScript + React + Tailwind CSS
- **Backend:** Azure Functions (integradas vía API Routes de Next.js)
- **Autenticación:** JWT en cookies HttpOnly
- **Base de datos:** Azure SQL Database
- **Almacenamiento:** Azure Blob Storage (SAS)
- **QR:** qrcode.react
- **Infraestructura:** Microsoft Azure

Arquitectura tipo **BFF (Backend for Frontend)**, donde Next.js actúa como capa de orquestación y seguridad hacia servicios backend desacoplados.

---

## Seguridad
- Autenticación por sesión con **JWT en cookie HttpOnly**
- Middleware de protección por rutas privadas
- Flujo obligatorio de cambio de contraseña
- Separación de roles y módulos operativos
- Tokens y SAS con alcance y vigencia limitada
- Validación pública controlada mediante QR/token

---

## Módulos y Funcionalidades Clave

### Reportes Ciudadanos
- Búsqueda de ciudadano por teléfono
- Alta y actualización de datos
- Creación de reportes
- Consulta por estatus
- Actualización de estatus y observaciones

---

### Jueces Auxiliares
- Registro mediante formulario por pasos
- Carga de INE a Azure Blob Storage
- Generación de QR para validación y asistencia
- Panel administrativo con filtros
- Consulta de visitas y control de asistencia

---

### Cartillas Militares
- Registro ciudadano por formulario multistep
- Panel operador para búsqueda de solicitudes
- Edición de datos
- Creación de trámite (matrícula)
- Confirmación y seguimiento del trámite

---

### Validación Pública
- Validación de asistencia de jueces auxiliares
- Acceso público controlado por QR/token
- Sin exposición de información sensible

---

## Decisiones Técnicas Clave
- **Next.js como BFF:** centraliza seguridad, sesiones y control de acceso hacia Azure Functions.
- **JWT en cookies HttpOnly:** reduce riesgo de exposición frente a almacenamiento en frontend.
- **Formularios multistep:** mejora experiencia de captura y reduce errores.
- **Azure Blob con SAS:** permite subir documentos sin exponer credenciales.
- **QR como mecanismo de validación:** elimina procesos manuales y facilita verificación en campo.

---

## Retos Técnicos
- Manejo de sesiones seguras en entorno web
- Integración limpia entre Next.js y Azure Functions
- Control de archivos sensibles (INE)
- Validación pública sin comprometer privacidad
- Modularización sin duplicar lógica

---

## Mi Rol en el Proyecto
- Diseño de la arquitectura web y de integración
- Desarrollo completo del frontend en Next.js
- Implementación de autenticación y middleware de seguridad
- Integración con Azure Functions y Blob Storage
- Diseño de flujos multistep y validación por QR
- Soporte y evolución funcional del sistema

---

## Evidencia Visual
Capturas anonimizadas del panel administrativo y flujos disponibles en la carpeta `/assets`.

---

## Estado
🟢 En operación / Evolución continua
