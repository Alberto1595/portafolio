# Automotive Showcase

Proyecto de demostración comercial y técnica para concesionarias automotrices, desarrollado como un monorepo con tres experiencias web independientes orientadas a distintos segmentos del mercado.

A diferencia de los sistemas institucionales y comerciales privados incluidos en este portafolio, este proyecto está pensado como una demostración pública de desarrollo frontend, arquitectura, calidad de software y experiencia de producto.

## Objetivo

Construir una base reutilizable para experiencias digitales de concesionarias sin convertir las distintas marcas o segmentos en simples variaciones de una misma plantilla.

El proyecto contempla tres aplicaciones:

- **Vehículos nuevos:** experiencia centrada en descubrimiento de modelos, configuración, cotización y prueba de manejo.
- **Seminuevos premium:** experiencia editorial orientada a evaluación detallada de unidades, especificaciones y confianza.
- **Seminuevos de valor:** experiencia enfocada en búsqueda rápida, precio, financiamiento y conversión.

## Arquitectura

El proyecto utiliza una arquitectura de monorepo que separa las aplicaciones comerciales de los paquetes técnicos compartidos.

Los paquetes comunes proporcionan:

- Primitivas reutilizables de interfaz.
- Tipos de dominio para vehículos.
- Contratos para acceso a inventario.
- Configuración estricta compartida de TypeScript.

Esta separación permite evolucionar cada experiencia visual de manera independiente manteniendo una base técnica consistente.

## Tecnologías

- TypeScript
- JavaScript
- Next.js
- React
- Tailwind CSS
- Node.js
- pnpm
- Turborepo
- Vitest
- Playwright
- ESLint
- Prettier
- GitHub

## Ingeniería de software

El proyecto se utiliza también como ejercicio de prácticas de ingeniería orientadas a producción:

- TypeScript en modo estricto.
- Separación entre dominio, datos, UI y aplicaciones.
- Componentes y paquetes compartidos con límites definidos.
- Linting sin advertencias aceptadas.
- Formateo automatizado.
- Pruebas unitarias.
- Pruebas E2E con Playwright.
- Builds de producción como parte de las verificaciones.
- Flujo de trabajo mediante issues, branches y pull requests.
- Integración continua y quality gates antes de integrar cambios.
- Documentación técnica y reglas de contribución.

## Flujo de desarrollo

Los cambios se trabajan mediante ramas dedicadas y pull requests en lugar de desarrollar directamente sobre `main`.

Flujo general:

`Issue / tarea → branch → implementación → verificación local → commit → push → Pull Request → CI → revisión → correcciones → merge`

Esto permite mantener trazabilidad sobre las decisiones y reducir regresiones conforme crece el proyecto.

## Enfoque de producto

Además del desarrollo técnico, el proyecto explora cómo adaptar una plataforma web al modelo comercial de una concesionaria:

- Catálogo e inventario de vehículos.
- Fichas de unidades y modelos.
- Navegación orientada a descubrimiento.
- Contacto y conversión comercial.
- Diseño responsive.
- SEO y metadata.
- Optimización de imágenes y rendimiento.
- Evolución futura hacia administración dinámica de inventario.

## Mi participación

- Diseño de la arquitectura del monorepo.
- Desarrollo frontend con Next.js, React y TypeScript.
- Diseño y evolución de las tres experiencias web.
- Definición de modelos de dominio e interfaces de inventario.
- Creación de componentes y paquetes compartidos.
- Configuración de herramientas de calidad.
- Implementación de pruebas unitarias y E2E.
- Gestión del desarrollo mediante Git y GitHub.
- Documentación técnica.
- Optimización progresiva de SEO, accesibilidad y rendimiento.

## Estado

**En desarrollo activo.**

La base de ingeniería está construida y las experiencias se desarrollan de forma incremental.

## Repositorio

El código del proyecto puede consultarse públicamente en GitHub:

[Ver Automotive Showcase en GitHub](https://github.com/Alberto1595/automotive-showcase)
