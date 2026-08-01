# POS Botmatica

Sistema integral de punto de venta desarrollado para administrar ventas, inventario, clientes, cajas, créditos y reportes operativos.

La solución está compuesta por:

- Una aplicación Android para la operación diaria en mostrador.
- Una aplicación web para administración, supervisión y reportes.
- Una API centralizada para procesar la lógica de negocio.
- Una base de datos PostgreSQL.

> El código fuente se mantiene privado por tratarse de un sistema comercial en operación. Este repositorio presenta su arquitectura, alcance funcional y tecnologías utilizadas.

## Estado del proyecto

**En producción y mejora continua.**

## Aplicación Android

Aplicación utilizada directamente por cajeros y personal operativo.

Funciones principales:

- Inicio de sesión de usuarios
- Apertura y cierre de caja
- Registro de fondo inicial
- Creación de ventas
- Búsqueda y selección de productos
- Aplicación de descuentos
- Cobro en efectivo
- Cobro mediante transferencia
- Pagos divididos
- Ventas a crédito
- Registro de clientes
- Consulta de caja actual
- Registro de retiros de efectivo
- Sincronización con el backend
- Distribución de versiones mediante Firebase App Distribution

## Aplicación web

Panel administrativo utilizado para supervisar la operación del negocio.

Funciones principales:

- Dashboard general
- Consulta e historial de ventas
- Historial de cajas
- Administración de productos y presentaciones
- Control de inventario
- Consulta de movimientos de inventario
- Gestión de clientes
- Historial de compras por cliente
- Administración de créditos
- Consulta de pagos y abonos
- Reportes diarios, semanales y mensuales
- Reportes por cajero
- Análisis de métodos de pago
- Consulta de productos más vendidos
- Alertas de inventario
- Generación de reportes y documentos PDF

## Arquitectura

La aplicación Android y la aplicación web se conectan mediante HTTPS a una API REST desarrollada con FastAPI.

El backend centraliza la lógica de negocio y se comunica con PostgreSQL para almacenar la información operativa.

Los servicios se ejecutan mediante contenedores Docker y son publicados mediante un proxy inverso Nginx.

## Tecnologías utilizadas

### Aplicación Android

- Kotlin
- Android SDK
- Jetpack Compose
- Retrofit
- Firebase App Distribution

### Aplicación web

- Next.js
- React
- TypeScript
- Tailwind CSS

### Backend

- Python
- FastAPI
- SQLAlchemy
- API REST
- Autenticación mediante tokens

### Infraestructura

- PostgreSQL
- Redis
- Docker
- Docker Compose
- Nginx
- Servidor VPS
- HTTPS

## Módulos principales

### Ventas

El sistema permite registrar ventas mediante:

- Efectivo
- Transferencia
- Enlace de pago
- Pago dividido
- Crédito

Cada venta conserva información sobre el cajero, cliente, productos, cantidades, precios, descuentos, método de pago y estado.

### Gestión de cajas

El sistema controla el ciclo completo de cada turno:

1. Apertura de caja
2. Registro de fondo inicial
3. Registro de ventas
4. Registro de abonos de crédito
5. Registro de retiros
6. Cálculo del efectivo esperado
7. Registro del efectivo contado
8. Cierre de caja

### Inventario

El módulo permite:

- Consultar existencias
- Administrar productos y presentaciones
- Registrar movimientos de inventario
- Identificar productos con bajo stock
- Calcular el valor total del inventario
- Mantener auditoría de modificaciones

### Clientes

Permite consultar:

- Datos generales
- Historial de compras
- Número de visitas
- Productos adquiridos
- Créditos pendientes
- Pagos realizados

### Créditos

Incluye:

- Registro de ventas a crédito
- Consulta de deuda pendiente
- Historial de abonos
- Abonos en efectivo
- Abonos mediante transferencia
- Reportes por cliente
- Documentos PDF con desglose de deuda

### Reportes

La aplicación web permite consultar:

- Ventas diarias
- Ventas semanales
- Ventas mensuales
- Ventas por periodo
- Ventas por cajero
- Métodos de pago
- Productos más vendidos
- Clientes frecuentes
- Historial de cajas
- Inventario disponible
- Créditos pendientes

## Operación multiestablecimiento

La arquitectura permite administrar diferentes establecimientos desde una misma plataforma, manteniendo separada la información de cada uno.

Cada establecimiento puede contar con sus propios productos, inventario, usuarios, cajas, clientes, ventas, créditos y reportes.

## Seguridad

- Comunicación cifrada mediante HTTPS
- Autenticación mediante tokens
- Control de acceso por usuario
- Separación de información por establecimiento
- Validación de operaciones desde el backend
- Auditoría de movimientos de inventario
- Credenciales administradas mediante variables de entorno
- Base de datos sin exposición directa a internet
- Proxy inverso mediante Nginx
- Respaldos de información

## Mi participación

- Diseño de arquitectura
- Desarrollo del backend
- Desarrollo y mantenimiento de la aplicación web
- Desarrollo y mantenimiento de la aplicación Android
- Diseño de base de datos
- Implementación de infraestructura con Docker
- Configuración del servidor y Nginx
- Desarrollo de módulos de ventas, cajas, inventario, clientes y créditos
- Generación de reportes
- Despliegue de versiones
- Soporte y mejora continua

## Resultados

- Digitalización del proceso de venta
- Control centralizado de inventario
- Seguimiento detallado de cajas
- Administración de créditos y abonos
- Consulta de información desde Android y web
- Reducción de procesos manuales
- Mayor trazabilidad de ventas y movimientos
- Reportes para la toma de decisiones

## Nota de confidencialidad

Por tratarse de un sistema comercial en operación, no se publican el código fuente, las credenciales, la información de clientes, los datos de ventas ni la configuración sensible de infraestructura.
