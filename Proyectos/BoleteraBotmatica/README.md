# Boletera Botmatica

Plataforma web para el registro de asistentes, emisión de boletos digitales, generación de códigos QR y control de acceso a eventos.

La solución permite administrar el proceso completo, desde el registro de una persona hasta la validación de su asistencia el día del evento.

> El código fuente se mantiene privado por tratarse de una solución comercial. Este repositorio presenta su arquitectura, alcance funcional y tecnologías utilizadas.

## Estado del proyecto

**En producción y mejora continua.**

## Descripción general

Boletera Botmatica fue desarrollada para digitalizar el registro y control de asistentes a eventos.

El sistema permite:

- Registrar participantes mediante un formulario web
- Generar folios únicos
- Emitir boletos digitales
- Generar códigos QR individuales
- Enviar confirmaciones por correo electrónico
- Descargar el boleto desde la pantalla de confirmación
- Validar boletos durante el acceso al evento
- Registrar la asistencia
- Evitar registros duplicados
- Consultar y administrar la información desde un panel web

## Flujo principal

1. El usuario ingresa al formulario de registro.
2. Captura sus datos personales y de contacto.
3. El backend valida la información.
4. El sistema verifica que no exista un registro duplicado.
5. Se genera un folio único.
6. Se crea un código QR asociado al registro.
7. Se almacena la información en la base de datos.
8. Se muestra una pantalla de confirmación.
9. El usuario puede descargar su boleto.
10. Se envía un correo electrónico con el folio y código QR.
11. Durante el evento, el personal escanea el QR.
12. El sistema valida el boleto y registra la asistencia.

## Formulario de registro

El sistema puede recopilar información como:

- Nombre completo
- Correo electrónico
- Número telefónico
- CURP o identificador definido por el evento
- Tipo de registro
- Categoría
- Información adicional solicitada por el organizador

Los campos pueden adaptarse de acuerdo con las necesidades de cada evento.

## Emisión de boletos

Cada registro genera un boleto digital con:

- Folio único
- Nombre del asistente
- Información del evento
- Tipo o categoría del boleto
- Código QR
- Indicaciones de acceso

El boleto puede entregarse mediante:

- Descarga directa desde el navegador
- Correo electrónico
- Impresión, cuando sea requerida por el organizador

## Código QR

Cada código QR está vinculado a un registro específico.

Durante el acceso, el sistema permite:

- Verificar que el boleto exista
- Consultar la información del participante
- Validar el estado del registro
- Detectar si el boleto ya fue utilizado
- Registrar fecha y hora de acceso
- Evitar ingresos duplicados

## Control de asistencia

El módulo de validación permite al personal del evento escanear boletos desde un dispositivo con navegador y cámara.

La validación informa si el boleto se encuentra:

- Válido
- Ya utilizado
- Cancelado
- No encontrado
- Pendiente de aprobación

Cuando el boleto es válido, el sistema registra la asistencia.

## Prevención de registros duplicados

El sistema implementa validaciones para evitar que una misma persona se registre más de una vez.

Dependiendo del evento, la detección puede realizarse mediante:

- CURP
- Correo electrónico
- Número telefónico
- Combinación de datos personales
- Identificadores cifrados o transformados

La validación se realiza desde el backend para evitar que pueda omitirse desde el navegador.

## Correos electrónicos

La plataforma envía correos de confirmación con:

- Nombre del participante
- Folio de registro
- Información del evento
- Código QR
- Indicaciones de acceso
- Enlace o archivo para consultar el boleto

El envío de correos se realiza mediante un proveedor transaccional.

## Panel administrativo

La plataforma contempla funciones administrativas para:

- Consultar registros
- Buscar asistentes
- Filtrar por categoría o estado
- Revisar folios
- Consultar asistencia
- Identificar registros duplicados
- Actualizar estados
- Exportar información
- Consultar estadísticas generales
- Administrar los datos del evento

## Arquitectura

La plataforma está compuesta por:

- Aplicación web desarrollada con Next.js
- Backend para validación y lógica de negocio
- Base de datos PostgreSQL
- Servicio de correo transaccional
- Generador de códigos QR
- Infraestructura desplegada mediante Docker

El navegador se comunica con el backend mediante HTTPS. El backend procesa las reglas de negocio, genera los folios y códigos QR, almacena los registros y coordina el envío de correos.

## Tecnologías utilizadas

### Aplicación web

- Next.js
- React
- TypeScript
- Tailwind CSS

### Backend

- Node.js
- API REST
- Validación de datos
- Generación de folios
- Generación y validación de códigos QR

### Base de datos

- PostgreSQL
- Restricciones de unicidad
- Índices para búsqueda
- Estados de registro y asistencia

### Infraestructura

- Docker
- Docker Compose
- Nginx
- Servidor Linux
- HTTPS
- Tailscale para acceso de administración y desarrollo

### Servicios externos

- Brevo para correo transaccional

## Modelo de información

Cada registro puede incluir:

- Identificador interno
- Folio
- Nombre
- Correo electrónico
- Teléfono
- Tipo de registro
- Categoría
- Estado
- Identificador utilizado para prevenir duplicados
- Código QR
- Fecha de creación
- Fecha de asistencia

## Estados del registro

Los registros pueden manejar estados como:

- Registrado
- Confirmado
- Pendiente
- Cancelado
- Asistencia registrada

Estos estados pueden adaptarse al flujo de cada evento.

## Seguridad

Entre las medidas implementadas se encuentran:

- Comunicación cifrada mediante HTTPS
- Validación de datos desde el backend
- Prevención de registros duplicados
- Identificadores sensibles almacenados mediante hash cuando aplica
- Restricciones de unicidad en base de datos
- Códigos QR vinculados a registros internos
- Validación del estado antes de registrar asistencia
- Variables de entorno para credenciales
- Base de datos sin exposición directa a internet
- Acceso administrativo controlado
- Registro de fecha y hora de validación

## Mi participación

Participé directamente en:

- Diseño de la arquitectura
- Desarrollo de la aplicación web
- Diseño del formulario de registro
- Desarrollo de la lógica de validación
- Implementación de prevención de duplicados
- Diseño de la base de datos
- Generación de folios
- Generación de códigos QR
- Creación del boleto digital
- Implementación de descarga de boletos
- Integración de correos transaccionales
- Desarrollo del flujo de validación de acceso
- Implementación del control de asistencia
- Configuración de Docker
- Despliegue y mantenimiento del sistema

## Resultados

- Digitalización del registro de asistentes
- Eliminación de listas manuales en papel
- Generación automática de folios y boletos
- Confirmaciones enviadas por correo
- Validación rápida mediante códigos QR
- Prevención de accesos duplicados
- Trazabilidad de registros y asistencias
- Reducción del tiempo de acceso durante eventos
- Información centralizada para los organizadores

## Adaptabilidad

La plataforma puede configurarse para distintos tipos de eventos, como:

- Eventos institucionales
- Conferencias
- Talleres
- Cursos
- Actividades culturales
- Eventos deportivos
- Entrega de apoyos
- Eventos con categorías o tipos de participante

## Nota de confidencialidad

Por tratarse de una solución comercial y de eventos reales, no se publican:

- Código fuente
- Credenciales
- Datos personales de participantes
- Códigos QR reales
- Folios reales
- Configuración interna
- Direcciones privadas de infraestructura
