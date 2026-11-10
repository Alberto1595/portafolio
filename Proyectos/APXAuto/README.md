# APX Auto

> Demo funcional de administración de inventario automotriz. Este caso presenta el alcance implementado y las decisiones técnicas; no publica código, credenciales ni datos privados.

---

## Descripción General

**APX Auto** es un panel administrativo para gestionar vehículos y alimentar un catálogo público. Demuestra el recorrido desde registrar una unidad y cargar sus fotografías hasta exponer su información para un sitio de venta.

Su valor es mostrar cómo una agencia puede actualizar información comercial desde un panel, sin editar la página por cada cambio de precio, estado o inventario.

---

## Objetivo del Proyecto

- Centralizar los datos comerciales de las unidades.
- Gestionar fotografías y disponibilidad desde una interfaz administrativa.
- Mostrar indicadores derivados del inventario almacenado.
- Conectar la administración con un catálogo público mediante una API.

---

## Arquitectura

**Stack tecnológico:**

- **Aplicación:** Next.js, React y TypeScript.
- **Backend de demo:** Server Actions y Route Handlers de Next.js.
- **Datos:** PostgreSQL administrado en Supabase, consultado desde servidor mediante PostgREST.
- **Archivos:** Supabase Storage.
- **Sesión:** cookie HttpOnly con firma HMAC y expiración.
- **Publicación:** Vercel; integración de catálogo con Vía Clara.

El panel y la API forman parte de la implementación de demo. Una futura separación a FastAPI está documentada como evolución, no como parte entregada de esta versión.

---

## Módulos y Funcionalidades Clave

### Acceso y Dashboard

- Inicio y cierre de sesión; protección de páginas y acciones administrativas.
- Indicadores de unidades totales, disponibles, apartadas y vendidas.
- Valor del inventario disponible, destacados y altas recientes.
- Estados diferenciados para configuración ausente, inventario vacío y errores.

### Gestión de Vehículos

- Listado, búsqueda y filtro por estado.
- Alta y edición de marca, modelo, versión, año, precio y kilometraje.
- Datos de transmisión, combustible, color y descripción.
- Estados disponible, apartado y vendido; selección de destacados.
- Validación del lado servidor y generación de identificadores de URL.

### Fotografías y Catálogo Público

- Carga de varias imágenes, selección de portada y eliminación.
- Restricciones de formato y tamaño.
- API pública limitada a información comercial de vehículos disponibles.
- Adaptador de Vía Clara para consumir el catálogo y conservar una alternativa demostrativa si el servicio no está configurado o falla.

---

## Seguridad

- Credenciales de datos y almacenamiento utilizadas exclusivamente en servidor.
- Verificación de sesión antes de las mutaciones administrativas.
- Sesiones firmadas y cookies HttpOnly.
- Validación de entradas y archivos.
- Separación entre información administrativa y respuesta pública del catálogo.

---

## Decisiones Técnicas Clave

- **Next.js full-stack para la demo:** permite validar el recorrido comercial sin añadir servicios innecesarios en esta etapa.
- **Modelo de agencia, vehículo y fotografías:** separa la unidad comercial de sus recursos multimedia.
- **Indicadores desde datos almacenados:** el dashboard refleja el inventario gestionado, en lugar de cifras decorativas.
- **Adaptador de catálogo:** conecta el panel con el sitio sin vincular los componentes visuales al proveedor de base de datos.

---

## Mi Rol en el Proyecto

- Diseño del alcance y recorrido administrativo.
- Modelado de vehículos, agencias y fotografías.
- Desarrollo de autenticación, dashboard y gestión de inventario.
- Integración de base de datos y almacenamiento.
- Desarrollo del endpoint público y su consumo desde Vía Clara.
- Documentación de configuración, validación y evolución del producto.

---

## Resultados

- Implementación de un recorrido administrativo que conecta datos, fotografías e información pública.
- Base para demostrar mantenimiento de inventario sin modificar código del sitio.
- Manejo explícito de estados vacíos, errores y dependencias sin configurar.

La documentación registra pruebas de acceso y protección del panel. La activación completa y el recorrido en un despliegue concreto dependen de su configuración; no se presenta como sistema de una agencia real en producción.

---

## Estado

Demo funcional / Preparada para validación comercial y evolución.
