# Sistema Clínico Botmatica

Plataforma web en desarrollo para la administración integral de clínicas y consultorios.

El sistema está diseñado para centralizar la información de pacientes, consultas, expedientes clínicos, citas, tratamientos, documentos y procesos administrativos dentro de una sola plataforma.

> El código fuente se mantiene privado por tratarse de una solución comercial en desarrollo. Este repositorio presenta el alcance funcional, la arquitectura propuesta y los módulos contemplados.

## Estado del proyecto

**En construcción.**

Actualmente se trabaja en el diseño de la arquitectura, el modelo de datos, los flujos operativos y los módulos principales del sistema.

## Objetivo

El objetivo de Sistema Clínico Botmatica es digitalizar y centralizar los procesos de atención médica, reduciendo el uso de expedientes físicos y facilitando el acceso controlado a la información clínica.

La plataforma busca permitir:

- Registro centralizado de pacientes
- Gestión de expedientes clínicos
- Programación y seguimiento de citas
- Registro de consultas médicas
- Control de tratamientos y diagnósticos
- Generación de documentos clínicos
- Consulta de antecedentes médicos
- Administración de usuarios y permisos
- Seguimiento administrativo de la clínica
- Trazabilidad de modificaciones y accesos

## Usuarios contemplados

### Administrador

- Administración de usuarios
- Asignación de roles y permisos
- Configuración de la clínica
- Gestión de catálogos
- Consulta de auditoría
- Supervisión operativa
- Administración de respaldos

### Médico

- Consulta de agenda
- Búsqueda de pacientes
- Acceso al expediente clínico
- Registro de consultas
- Captura de diagnósticos
- Registro de signos vitales
- Prescripción de medicamentos
- Indicación de estudios
- Seguimiento de tratamientos
- Generación de recetas y documentos clínicos

### Recepción

- Registro de pacientes
- Programación de citas
- Reprogramación y cancelación
- Confirmación de asistencia
- Consulta de disponibilidad
- Gestión de datos de contacto
- Seguimiento de pacientes pendientes

### Personal clínico

Se contemplan perfiles adicionales como enfermería, laboratorio, asistente médico, caja y supervisión.

Cada perfil tendrá acceso únicamente a los módulos necesarios para su función.

## Módulos principales

### Pacientes

El módulo permitirá registrar:

- Nombre completo
- Fecha de nacimiento
- Sexo
- Datos de contacto
- Domicilio
- Contacto de emergencia
- Alergias
- Tipo sanguíneo
- Antecedentes personales
- Antecedentes familiares
- Enfermedades crónicas
- Medicamentos actuales
- Observaciones generales

### Expediente clínico

Cada paciente contará con un expediente clínico digital que podrá integrar:

- Datos generales
- Historial de consultas
- Signos vitales
- Antecedentes médicos
- Diagnósticos
- Tratamientos
- Recetas
- Estudios solicitados
- Resultados clínicos
- Alergias
- Archivos adjuntos
- Notas médicas
- Evolución del paciente

### Consultas

Cada consulta podrá registrar:

- Fecha y hora
- Médico responsable
- Motivo de consulta
- Síntomas
- Exploración
- Signos vitales
- Impresión diagnóstica
- Diagnósticos
- Tratamiento
- Medicamentos
- Estudios solicitados
- Recomendaciones
- Próxima consulta
- Notas de seguimiento

### Citas

El módulo permitirá:

- Programar citas
- Consultar disponibilidad
- Asignar médico
- Definir duración
- Registrar motivo
- Reprogramar
- Cancelar
- Confirmar asistencia
- Registrar llegada
- Marcar consulta completada
- Identificar ausencias

Estados contemplados:

- Programada
- Confirmada
- En espera
- En consulta
- Completada
- Cancelada
- No asistió

### Signos vitales

- Peso
- Estatura
- Temperatura
- Presión arterial
- Frecuencia cardiaca
- Frecuencia respiratoria
- Saturación de oxígeno
- Glucosa
- Índice de masa corporal

### Diagnósticos

- Diagnóstico principal
- Diagnósticos secundarios
- Descripción clínica
- Fecha de detección
- Estado
- Observaciones
- Relación con tratamientos y estudios

### Medicamentos y recetas

- Catálogo de medicamentos
- Nombre comercial y genérico
- Presentación
- Dosis
- Frecuencia
- Duración
- Vía de administración
- Indicaciones
- Advertencias
- Fecha de emisión
- Médico responsable

Las recetas podrán generarse en formato PDF.

### Tratamientos

- Nombre
- Fecha de inicio
- Fecha de finalización
- Indicaciones
- Medicamentos relacionados
- Sesiones
- Evolución
- Estado
- Observaciones

### Estudios clínicos

- Tipo de estudio
- Fecha de solicitud
- Motivo
- Indicaciones
- Estado
- Fecha de realización
- Resultados
- Archivos adjuntos
- Observaciones médicas

### Documentos

- Recetas médicas
- Resúmenes clínicos
- Indicaciones
- Solicitudes de estudios
- Constancias
- Consentimientos informados
- Notas médicas
- Reportes de consulta

### Archivos clínicos

- Resultados de laboratorio
- Estudios de imagen
- Documentos PDF
- Fotografías clínicas
- Consentimientos
- Documentación administrativa

### Panel administrativo

- Pacientes registrados
- Citas del día
- Consultas realizadas
- Citas canceladas
- Pacientes pendientes
- Médicos activos
- Actividad reciente
- Indicadores operativos
- Accesos y modificaciones
- Estado general del sistema

## Flujo general de atención

1. Recepción registra o localiza al paciente.
2. Se programa o confirma la cita.
3. Se actualizan sus datos.
4. Se registran signos vitales.
5. El médico abre el expediente.
6. Se documenta la consulta.
7. Se registran diagnósticos y tratamientos.
8. Se generan recetas o solicitudes.
9. Se programa seguimiento.
10. La información queda integrada en el historial.

## Arquitectura propuesta

La solución está diseñada bajo una arquitectura web cliente-servidor.

### Aplicación web

- Formularios clínicos
- Agenda
- Expedientes
- Reportes
- Administración

### Backend

- Autenticación
- Autorización
- Reglas de negocio
- Validación
- Acceso a base de datos
- Auditoría
- Generación de documentos
- Gestión de archivos

### Base de datos

- Usuarios
- Roles
- Pacientes
- Citas
- Consultas
- Signos vitales
- Diagnósticos
- Medicamentos
- Tratamientos
- Estudios
- Documentos
- Auditoría

### Almacenamiento de archivos

Los documentos y estudios se almacenarán de forma privada, manteniendo en la base de datos sus referencias y metadatos.

## Tecnologías contempladas

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

### Base de datos

- PostgreSQL

### Infraestructura

- Docker
- Docker Compose
- Nginx
- Servidor Linux
- HTTPS
- Almacenamiento privado
- Sistema de respaldos

## Modelo de datos propuesto

- Clínicas
- Usuarios
- Roles
- Permisos
- Médicos
- Pacientes
- Contactos de emergencia
- Citas
- Consultas
- Signos vitales
- Antecedentes
- Alergias
- Diagnósticos
- Medicamentos
- Recetas
- Tratamientos
- Estudios
- Archivos
- Documentos
- Auditoría

## Seguridad

- Comunicación cifrada mediante HTTPS
- Autenticación de usuarios
- Control de acceso basado en roles
- Permisos por módulo
- Contraseñas almacenadas mediante hash seguro
- Expiración controlada de sesiones
- Validación desde el backend
- Registro de accesos y modificaciones
- Auditoría de operaciones sensibles
- Variables de entorno para credenciales
- Base de datos sin exposición pública
- Acceso restringido a archivos clínicos
- Respaldos periódicos
- Recuperación ante fallos
- Minimización de datos visibles por usuario

## Auditoría

El sistema contempla registrar:

- Inicio y cierre de sesión
- Acceso a expedientes
- Creación de pacientes
- Modificación de datos
- Registro de consultas
- Cambios en diagnósticos
- Generación de documentos
- Carga y descarga de archivos
- Cancelación de registros
- Cambios de permisos

## Funcionalidades futuras

- Recordatorios de citas
- Confirmaciones mediante WhatsApp
- Portal para pacientes
- Firma digital
- Teleconsulta
- Facturación
- Control de pagos
- Inventario médico
- Integración con laboratorios
- Estadísticas clínicas
- Exportación de expedientes
- Aplicación móvil
- Gestión multi-clínica
- Plantillas por especialidad
- Integración con dispositivos médicos

## Diseño multi-clínica

La arquitectura contempla administrar múltiples clínicas o consultorios, manteniendo separados:

- Pacientes
- Médicos
- Usuarios
- Citas
- Consultas
- Configuración
- Documentos
- Reportes

## Mi participación

- Levantamiento de requerimientos
- Diseño funcional
- Diseño de arquitectura
- Modelado de base de datos
- Desarrollo de la aplicación web
- Desarrollo del backend
- Diseño de roles y permisos
- Implementación de seguridad
- Diseño de expedientes clínicos
- Desarrollo de agenda y citas
- Generación de documentos
- Infraestructura con Docker
- Configuración del servidor
- Diseño de respaldos
- Pruebas
- Despliegue
- Mantenimiento

## Resultados esperados

- Centralización de expedientes clínicos
- Reducción del uso de papel
- Acceso rápido al historial
- Mayor trazabilidad
- Mejor organización de citas
- Control de acceso a información sensible
- Generación automatizada de documentos
- Seguimiento clínico estructurado
- Reducción de errores administrativos

## Etapas de desarrollo

### Etapa 1

- Arquitectura
- Modelo de datos
- Usuarios y roles
- Registro de pacientes
- Agenda y citas

### Etapa 2

- Expediente clínico
- Consultas
- Signos vitales
- Diagnósticos
- Recetas

### Etapa 3

- Estudios
- Archivos clínicos
- Documentos PDF
- Auditoría
- Reportes

### Etapa 4

- Notificaciones
- Portal de pacientes
- Módulos administrativos
- Funciones multi-clínica
- Integraciones externas

## Nota de confidencialidad

Al tratarse de una solución clínica en desarrollo, no se publicarán el código fuente, credenciales, datos de pacientes, expedientes clínicos, documentos médicos reales ni configuración sensible.
