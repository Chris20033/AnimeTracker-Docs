---
title: Roadmap de Desarrollo
tags:
  - animetracker/roadmap
estado: migrado
fuente:
  - 8_Roadmap_de_desarrollo.docx
---

# Roadmap de Desarrollo

El roadmap divide la construcción de AnimeTracker en fases pequeñas y manejables. Cada fase debe generar un producto funcional que pueda probarse antes de continuar.

## Fase 1 Preparación del Proyecto

Objetivo: configurar el entorno de desarrollo y establecer la base técnica.

Actividades:

- Crear repositorio en GitHub.
- Configurar frontend con React y Vite.
- Configurar backend con Node.js y Express.
- Configurar PostgreSQL.
- Configurar Prisma.
- Configurar Docker.
- Configurar variables de entorno.
- Configurar ESLint y Prettier.
- Definir estructura de carpetas.

Entregable: proyecto funcional con frontend, backend y base de datos conectados.

Duración estimada: 1 semana.

## Fase 2 Sistema de Autenticación

Objetivo: implementar acceso seguro al sistema.

Actividades:

- Registro de usuarios.
- Inicio de sesión.
- Cierre de sesión.
- Hash de contraseñas.
- JWT.
- Middleware de autenticación.
- Protección de rutas.
- Recuperación de contraseña.

Entregable: usuarios capaces de crear cuentas e iniciar sesión.

Duración estimada: 1 a 2 semanas.

## Fase 3 Gestión de Perfil

Objetivo: permitir administración de perfiles personales.

Actividades:

- Consultar perfil.
- Editar perfil.
- Actualizar avatar.
- Actualizar banner.
- Actualizar biografía.
- Consultar perfil público.

Entregable: sistema completo de perfiles de usuario.

Duración estimada: 1 semana.

## Fase 4 Integración con API de Anime

Objetivo: permitir consulta de información de anime.

Actividades:

- Integración con Jikan API.
- Búsqueda de anime.
- Detalle de anime.
- Manejo de errores.
- Paginación.

Entregable: usuarios capaces de buscar anime y consultar información detallada.

Duración estimada: 1 semana.

## Fase 5 Biblioteca Personal

Objetivo: implementar la funcionalidad principal de AnimeTracker.

Actividades:

- Agregar anime a biblioteca.
- Actualizar estado.
- Actualizar progreso.
- Registrar calificación.
- Registrar notas.
- Eliminar anime de biblioteca.

Entregable: biblioteca personal funcional.

Duración estimada: 1 a 2 semanas.

## Fase 6 Favoritos

Objetivo: permitir gestión de anime favoritos.

Actividades:

- Agregar favoritos.
- Eliminar favoritos.
- Mostrar favoritos en perfil.

Entregable: sistema de favoritos funcional.

Duración estimada: 3 a 5 días.

## Fase 7 Comentarios Generales

Objetivo: permitir interacción básica entre usuarios.

Actividades:

- Crear comentarios.
- Editar comentarios.
- Eliminar comentarios.
- Mostrar comentarios por anime.

Entregable: sistema básico de comunidad.

Duración estimada: 1 semana.

## Fase 8 Seguidores

Objetivo: implementar relaciones sociales entre usuarios.

Actividades:

- Seguir usuarios.
- Dejar de seguir usuarios.
- Mostrar seguidores.
- Mostrar seguidos.

Entregable: sistema social básico.

Duración estimada: 1 semana.

## Fase 9 Estadísticas

Objetivo: generar información útil para el usuario.

Actividades:

- Anime completados.
- Episodios vistos.
- Promedio de calificaciones.
- Géneros favoritos.
- Distribución por estado.

Entregable: panel estadístico funcional.

Duración estimada: 1 semana.

## Fase 10 Mejoras de Interfaz

Objetivo: incrementar la calidad visual del sistema.

Actividades:

- Diseño responsivo.
- Skeleton loaders.
- Estados de carga.
- Estados vacíos.
- Mejoras visuales.
- Accesibilidad básica.

Entregable: interfaz moderna y profesional.

Duración estimada: 1 semana.

## Fase 11 Despliegue

Objetivo: publicar el proyecto para acceso público.

Actividades:

- Deploy del frontend.
- Deploy del backend.
- Configuración de PostgreSQL.
- Variables de entorno de producción.
- Pruebas de funcionamiento.

Entregable: proyecto accesible desde Internet.

Duración estimada: 3 a 5 días.

## Fase 12 Documentación Final

Objetivo: preparar el proyecto para portafolio profesional.

Actividades:

- README profesional.
- Capturas de pantalla.
- Diagrama entidad-relación.
- Diagrama de arquitectura.
- Guía de instalación.
- Guía de despliegue.

Entregable: proyecto listo para presentación a reclutadores.

Duración estimada: 3 a 5 días.

## Fase 13 Integración CI/CD

Objetivo: automatizar validación, construcción y despliegue.

Actividades:

- Configurar GitHub Actions.
- Instalar dependencias automáticamente.
- Ejecutar linters.
- Ejecutar pruebas automatizadas.
- Validar build del frontend.
- Validar build del backend.
- Configurar despliegue automático.
- Proteger ramas principales.
- Ejecutar pipeline en push o pull request.

Entregable: pipeline CI/CD funcional.

Duración estimada: 1 semana.

## Referencias Relacionadas

- [[Roadmap Visual]]
- [[Plan de Sprints]]
- [[MVP]]
- [[Funcionalidades Futuras]]
