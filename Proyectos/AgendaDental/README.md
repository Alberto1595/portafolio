# APX Agenda — Agenda Dental por WhatsApp

> Demo de automatización de citas. Se presenta el alcance desarrollado y las validaciones documentadas, sin publicar código, datos de pacientes, teléfonos de prueba ni credenciales.

---

## Descripción General

**APX Agenda** es una solución de reserva y cancelación de citas mediante WhatsApp. El usuario elige un día y un bloque disponible, revisa sus datos y confirma dentro de la conversación.

Su valor está en coordinar conversación, disponibilidad y persistencia: una respuesta del bot debe corresponder a una operación registrada, incluso ante mensajes repetidos, fallas de transporte o intentos de reservar el mismo horario.

---

## Objetivo del Proyecto

- Automatizar la consulta de disponibilidad, reserva y cancelación.
- Evitar dobles reservas desde la base de datos.
- Mantener conversaciones recuperables y operaciones trazables.
- Integrar eventos de agenda con Google Calendar y correo transaccional.
- Preparar recordatorios y herramientas del doctor con activación controlada.

---

## Arquitectura

**Stack tecnológico:**

- **Backend HTTP:** Next.js sobre Vercel, con módulos de dominio en JavaScript/Node.js.
- **Datos:** PostgreSQL en Supabase y funciones transaccionales de agenda.
- **Mensajería:** API de Meta WhatsApp, webhook autenticado y workers de procesamiento.
- **Integraciones:** Google Calendar con OAuth y correo mediante Brevo.
- **Consistencia:** conversaciones persistentes, deduplicación, cola de trabajos y outbox transaccional.
- **Pruebas:** Node Test Runner, PGlite y validaciones documentadas en PostgreSQL remoto.

PostgreSQL conserva la disponibilidad y las citas. Calendar recibe una representación de la agenda; la versión desarrollada no depende de editar manualmente Google Calendar para determinar reservas.

---

## Módulos y Funcionalidades Clave

### Conversación y Reservas

- Selección de demo, captura de nombre y consulta de días y horarios.
- Fechas de los próximos 30 días, con paginación para respetar los límites de listas de WhatsApp.
- Resumen y confirmación mediante controles interactivos.
- Consulta de citas propias y cancelación con confirmación.
- Liberación del bloque al cancelar y nueva comprobación de disponibilidad al reservar.

### Integridad y Recuperación

- Restricciones de base de datos para impedir dos citas activas en el mismo bloque.
- Persistencia de la cita y sus efectos pendientes en la misma transacción.
- Mensajes repetidos que recuperan el resultado sin crear otra reserva.
- Rechazo de acciones antiguas o pertenecientes a otra conversación.
- Trabajos con reintentos acotados y revisión de envíos cuyo resultado sea incierto.

### Integraciones y Operación

- Adaptadores de alta y cancelación en Google Calendar y correo.
- Identidad estable de eventos para reconciliar reintentos sin crear copias deliberadas.
- Núcleo de consentimiento y programación de recordatorios.
- Herramientas para bloquear/liberar horarios y registrar asistencia, disponibles solo para doctores autorizados en servidor.

---

## Seguridad

- Verificación de firma del webhook y receptores permitidos.
- Identidad del usuario obtenida del evento autenticado, no de un teléfono arbitrario escrito en el chat.
- Separación por negocio, proveedor y conversación.
- Acceso a datos desde servidor y endpoints internos autenticados.
- Autorización del doctor independiente de los botones o textos que envíe.

---

## Decisiones Técnicas Clave

- **La base de datos protege el horario:** evita depender de una consulta previa que pueda quedar obsoleta.
- **Conversación separada del transporte:** permite evolucionar el canal sin duplicar reglas de agenda.
- **Integraciones mediante trabajos persistentes:** un fallo externo puede recuperarse sin perder la cita registrada.
- **Resultado incierto a revisión:** evita repetir automáticamente un envío cuando no se conoce si el proveedor ya lo aceptó.

---

## Mi Rol en el Proyecto

- Diseño de flujos de paciente y operación del doctor.
- Arquitectura de conversaciones, agenda e integraciones.
- Modelado relacional y reglas de reserva/cancelación.
- Implementación del webhook, persistencia y procesamiento de mensajes.
- Integración con Calendar y correo; desarrollo de recuperación y deduplicación.
- Preparación de pruebas funcionales y de integridad.
- Ajustes del diálogo, paginación de fechas y botones de confirmación.

---

## Resultados

- Demo con reserva, consulta y cancelación apoyadas en almacenamiento persistente.
- Protección de reserva única validada en pruebas documentadas con sesiones PostgreSQL independientes.
- Pruebas documentadas de reinicio, rollback, repetición de eventos y fallas de integraciones.
- Base reutilizable de transporte y conversación, también utilizada por la demo de pedidos de Patio 11.

La activación de proveedores depende del entorno. Los recordatorios, plantillas, programación periódica y herramientas del doctor requieren completar su validación y configuración antes de una entrega clínica; no se presentan como servicios productivos ya operando para pacientes.

---

## Estado

Demo funcional / Integraciones y operación en validación. No corresponde a un sistema clínico en producción.
