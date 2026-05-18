# Barandillas

> ⚠️ El código fuente de este proyecto es privado debido a confidencialidad institucional.  
> Este documento describe la funcionalidad, arquitectura y decisiones técnicas del sistema.

---

## Descripción General
**Barandillas** es un sistema de gestión de detenidos desarrollado para el **C4 Cadereyta Jiménez**, diseñado para digitalizar y centralizar el registro, seguimiento y control de personas detenidas en el municipio.

El sistema opera en intranet municipal con acceso restringido por rol, permitiendo al personal autorizado registrar ingresos, consultar historial, generar documentos oficiales y mantener respaldo seguro de la información.

---

## Objetivo del Proyecto
- Digitalizar el registro de detenidos eliminando procesos en papel
- Centralizar la información en un sistema seguro de acceso controlado
- Facilitar la búsqueda y consulta de historial por operadores
- Automatizar la generación de documentos y reportes oficiales
- Garantizar respaldo y trazabilidad de la información

---

## Arquitectura

**Stack tecnológico:**

- **Frontend:** Next.js (App Router) + TypeScript + React + Tailwind CSS
- **Backend:** FastAPI (Python)
- **Base de datos:** PostgreSQL (producción local) + Azure SQL Database (respaldo)
- **Almacenamiento:** Local (fotos) + Azure Blob Storage (respaldo)
- **Infraestructura:** Docker + Nginx (reverse proxy) + Tailscale (acceso remoto seguro)
- **Servidor:** Ubuntu 24.04 (on-premise)

Arquitectura cliente-servidor desacoplada, desplegada en red interna municipal con acceso remoto exclusivamente mediante túnel Tailscale — sin puertos expuestos a internet.

---

## Seguridad
- Acceso remoto únicamente vía **Tailscale** — sin exposición pública de puertos
- Autenticación con **JWT en cookies HttpOnly**
- **Control de acceso por rol** — operadores, supervisores y administradores
- **HTTPS interno** mediante mkcert
- Hardening del servidor: UFW, Fail2ban, SSH key-only auth
- Respaldo cifrado en Azure SQL y Blob Storage
- Sin exposición de datos sensibles fuera de la intranet

---

## Módulos y Funcionalidades Clave

### Registro de Detenidos
- Captura de datos personales y motivo de detención
- Carga y almacenamiento de fotografía
- Registro de fecha, hora y personal responsable

### Búsqueda y Consulta
- Búsqueda por nombre, fecha, folio o motivo
- Historial completo por detenido
- Filtros por rango de fechas y estatus

### Gestión de Usuarios y Roles
- Alta y baja de usuarios del sistema
- Asignación de roles con permisos diferenciados
- Trazabilidad de acciones por usuario

### Reportes y Generación de Archivos
- Generación de documentos oficiales por detenido
- Reportes por turno, fecha y operador
- Exportación para control administrativo

---

## Decisiones Técnicas Clave
- **FastAPI + Next.js desacoplados:** separa claramente la lógica de negocio del frontend, facilitando mantenimiento independiente de cada capa.
- **PostgreSQL local como fuente de verdad:** garantiza operación continua sin depender de conectividad a internet — crítico en entorno de seguridad pública.
- **Respaldo dual en Azure:** SQL para datos relacionales y Blob para archivos, asegurando recuperación ante falla del servidor local.
- **Tailscale como única puerta de acceso remoto:** elimina la necesidad de exponer puertos al exterior, reduciendo drásticamente la superficie de ataque.
- **Docker para portabilidad:** permite redeployment rápido ante falla de hardware sin reconfiguración manual del entorno.

---

## Retos Técnicos
- Garantizar operación offline ante pérdida de conectividad
- Sincronización consistente entre almacenamiento local y respaldo en Azure
- Control de acceso granular en entorno de seguridad pública
- Manejo seguro de fotografías e información sensible de detenidos
- Despliegue en infraestructura on-premise con recursos limitados

---

## Mi Rol en el Proyecto
- Diseño completo de la arquitectura del sistema
- Desarrollo del backend en FastAPI y base de datos en PostgreSQL
- Desarrollo del frontend en Next.js
- Implementación de autenticación, roles y middleware de seguridad
- Configuración de infraestructura: Docker, Nginx, Tailscale, UFW, Fail2ban
- Integración de respaldo en Azure SQL y Blob Storage
- Despliegue y puesta en producción en servidor on-premise
- Soporte y evolución continua del sistema

---

## Resultados
- **~20 registros diarios** de detenidos en operación activa
- **6 usuarios** con roles diferenciados operando el sistema
- **3 meses** en producción sin interrupciones
- Eliminación completa del registro en papel
- Trazabilidad total de acciones por operador y turno

---

## Estado
En operación / Evolución continua
