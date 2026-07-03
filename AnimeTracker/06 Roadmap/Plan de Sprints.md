---
title: Plan de Sprints
tags:
  - animetracker/roadmap
  - animetracker/sprints
estado: activo
---

# Plan de Sprints

Este plan organiza el desarrollo completo de AnimeTracker para una sola persona trabajando backend y frontend. Cada sprint está pensado para generar un avance verificable y profesional.

Duración sugerida: 1 semana por sprint.

## Reglas de Trabajo

- [ ] Antes de implementar, revisar la documentación relacionada desde [[AnimeTracker - Índice]].
- [ ] Mantener backend, frontend, API y documentación sincronizados.
- [ ] Actualizar checkboxes al terminar tareas.
- [ ] Ejecutar pruebas, lint o build antes de cerrar cada sprint.
- [ ] Si cambia un endpoint, actualizar la nota correspondiente en [[API REST]].
- [ ] Si cambia la base de datos, actualizar [[Diseño Lógico]], [[Diccionario de Datos]] y [[Diagrama ER]].

## Sprint 0 - Preparación Profesional

Objetivo: crear la base técnica del proyecto y dejar listo el entorno local.

Entregable: proyecto base ejecutable con frontend, backend y base de datos local.

### Backend

- [x] Crear estructura `backend/`.
- [x] Inicializar proyecto Node.js.
- [x] Instalar Express.
- [x] Crear `server` base.
- [x] Crear endpoint `GET /health`.
- [x] Configurar variables de entorno.
- [x] Configurar manejo base de errores.

### Frontend

- [x] Crear estructura `frontend/`.
- [x] Configurar Vite + React.
- [x] Configurar React Router.
- [x] Configurar Tailwind CSS.
- [x] Crear layout base.
- [x] Crear página inicial temporal.
- [x] Configurar cliente HTTP base.

### DevOps y Calidad

- [x] Crear repositorio en GitHub.
- [x] Configurar `.gitignore`.
- [ ] Configurar ESLint.
- [ ] Configurar Prettier.
- [x] Configurar Docker Compose.
- [x] Configurar PostgreSQL local.
- [x] Configurar Adminer o pgAdmin.

### Documentación

- [ ] Documentar setup local.
- [ ] Actualizar [[Despliegue]] si cambian variables o comandos.
- [ ] Validar que el índice siga enlazando correctamente.

### Criterio de Cierre

- [ ] Frontend corre localmente.
- [x] Backend corre localmente.
- [x] PostgreSQL corre localmente.
- [x] `GET /health` responde correctamente.

## Sprint 1 - Base Backend y Base de Datos

Objetivo: crear la base persistente del sistema y estructura backend profesional.

Entregable: Prisma configurado con modelos iniciales y migraciones.

### Backend

- [x] Instalar Prisma.
- [x] Configurar `DATABASE_URL`.
- [x] Crear `schema.prisma` inicial.
- [x] Crear modelos `User`, `PasswordResetToken`, `Anime`, `Genre`, `UserAnimeList`, `Favorite`.
- [x] Crear enums `Role` y `LibraryStatus`.
- [x] Crear migración inicial.
- [x] Configurar cliente Prisma.
- [x] Crear estructura `controllers`, `services`, `repositories`, `routes`, `middlewares`, `schemas`, `utils`.
- [x] Crear middleware centralizado de errores.
- [x] Crear formato estándar de respuesta.
- [x] Crear formato estándar de error.

### Frontend

- [x] Definir estructura de carpetas frontend.
- [x] Crear configuración base de rutas.
- [x] Crear componentes base reutilizables.
- [x] Crear estilos globales.

### Testing y Calidad

- [x] Verificar conexión backend-PostgreSQL.
- [x] Ejecutar migración local.
- [x] Probar health check.
- [x] Ejecutar lint.

### Documentación

- [ ] Revisar [[Diseño Lógico]].
- [ ] Revisar [[Diccionario de Datos]].
- [ ] Revisar [[Diagrama ER]].
- [ ] Actualizar documentación si el schema implementado difiere.

### Criterio de Cierre

- [x] Migraciones aplicadas localmente.
- [x] Backend compila/arranca sin errores.
- [x] Estructura por capas creada.

## Sprint 2 - Autenticación

Objetivo: permitir registro, login, logout lógico y protección de rutas.

Entregable: usuarios pueden crear cuenta, iniciar sesión y acceder a rutas protegidas.

### Backend

- [x] Implementar `POST /api/auth/register`.
- [x] Implementar `POST /api/auth/login`.
- [x] Implementar `POST /api/auth/logout`.
- [x] Implementar hashing con bcrypt.
- [x] Implementar generación de JWT.
- [x] Implementar middleware de autenticación.
- [x] Validar datos con Zod.
- [x] Validar username único.
- [x] Validar email único.
- [x] Validar usuario activo.

### Frontend

- [x] Crear página de registro.
- [x] Crear página de login.
- [x] Crear formularios con validación visual.
- [x] Crear store de sesión.
- [x] Guardar token de forma controlada.
- [x] Crear rutas protegidas.
- [x] Crear logout desde UI.

### Testing y Calidad

- [x] Probar registro exitoso.
- [x] Probar username duplicado.
- [x] Probar email duplicado.
- [x] Probar login exitoso.
- [x] Probar credenciales inválidas.
- [x] Probar ruta protegida sin token.

### Documentación

- [x] Revisar [[Endpoints - Autenticación]].
- [ ] Actualizar contratos si cambia request o response.
- [x] Revisar [[Autenticación y Seguridad]].

### Criterio de Cierre

- [x] Usuario puede registrarse.
- [x] Usuario puede iniciar sesión.
- [x] Usuario puede cerrar sesión.
- [x] Rutas privadas rechazan usuarios no autenticados.

## Sprint 3 - Recuperación de Contraseña

Objetivo: permitir recuperación segura de contraseña con token temporal.

Entregable: flujo completo de recuperación funcionando en entorno local.

### Backend

- [x] Implementar `POST /api/auth/forgot-password`.
- [x] Implementar `POST /api/auth/reset-password`.
- [x] Generar tokens seguros.
- [x] Guardar expiración del token.
- [x] Marcar tokens usados.
- [x] Evitar reutilización de token.
- [x] Configurar proveedor de email o modo desarrollo.
- [x] Evitar enumeración de correos.

### Frontend

- [x] Crear página `Olvidé mi contraseña`.
- [x] Crear página `Restablecer contraseña`.
- [x] Mostrar mensajes claros de éxito/error.
- [x] Validar nueva contraseña.
- [x] Crear botón light/dark mode

### Testing y Calidad

- [x] Probar solicitud de recuperación.
- [x] Probar reset con token válido.
- [x] Probar reset con token expirado.
- [x] Probar reset con token ya usado.

### Documentación

- [x] Revisar [[Endpoints - Autenticación]].
- [x] Revisar [[Autenticación y Seguridad]].
- [ ] Actualizar [[Despliegue]] con variables de email si aplica.

### Criterio de Cierre

- [x] Usuario puede solicitar recuperación.
- [x] Usuario puede cambiar contraseña con token válido.
- [x] Tokens inválidos, expirados o usados son rechazados.

## Sprint 4 - Perfil de Usuario

Objetivo: implementar perfil privado, edición y perfil público.

Entregable: usuario puede gestionar su perfil y compartir perfil público.

### Backend

- [ ] Implementar `GET /api/users/me`.
- [ ] Implementar `PATCH /api/users/me`.
- [ ] Implementar `GET /api/users/:username`.
- [ ] Validar username único al editar.
- [ ] Evitar exponer campos sensibles.

### Frontend

- [ ] Crear página de perfil privado.
- [ ] Crear formulario de edición.
- [ ] Crear página de perfil público.
- [ ] Mostrar avatar, banner, username y biografía.
- [ ] Preparar secciones para favoritos y estadísticas públicas.

### Testing y Calidad

- [ ] Probar consulta de perfil privado.
- [ ] Probar actualización de perfil.
- [ ] Probar username duplicado.
- [ ] Probar perfil público inexistente.

### Documentación

- [ ] Revisar [[Endpoints - Usuarios]].
- [ ] Revisar [[Requisitos Funcionales#RF-04 Gestión de Perfil]].
- [ ] Revisar [[Requisitos Funcionales#RF-05 Perfil Público]].

### Criterio de Cierre

- [ ] Usuario edita su perfil.
- [ ] Perfil público es visible por username.
- [ ] No se exponen datos sensibles.

## Sprint 5 - Anime Search y Detail

Objetivo: integrar búsqueda y detalle de anime usando Jikan API desde backend.

Entregable: usuario puede buscar anime y consultar detalle.

### Backend

- [ ] Crear cliente para Jikan API.
- [ ] Implementar `GET /api/anime/search`.
- [ ] Implementar `GET /api/anime/:source/:externalId`.
- [ ] Normalizar respuesta externa.
- [ ] Manejar errores de API externa.
- [ ] Implementar paginación.

### Frontend

- [ ] Crear página de búsqueda.
- [ ] Crear campo de búsqueda.
- [ ] Crear lista/grid de resultados.
- [ ] Crear página de detalle.
- [ ] Mostrar imagen, título, sinopsis, episodios, géneros, score y estado.
- [ ] Implementar loading/error/empty states.
- [ ] Implementar paginación.

### Testing y Calidad

- [ ] Probar búsqueda con resultados.
- [ ] Probar búsqueda sin resultados.
- [ ] Probar detalle válido.
- [ ] Probar fallo de API externa.

### Documentación

- [ ] Revisar [[Endpoints - Anime]].
- [ ] Revisar [[Integraciones Externas]].

### Criterio de Cierre

- [ ] Usuario busca anime.
- [ ] Usuario abre detalle.
- [ ] Frontend no consume Jikan directamente.

## Sprint 6 - Biblioteca Personal

Objetivo: implementar la funcionalidad principal de seguimiento de anime.

Entregable: usuario puede administrar su biblioteca personal.

### Backend

- [ ] Implementar `GET /api/library`.
- [ ] Implementar `POST /api/library`.
- [ ] Implementar `PATCH /api/library/:id`.
- [ ] Implementar `DELETE /api/library/:id`.
- [ ] Persistir anime al agregarlo si no existe.
- [ ] Validar anime duplicado por usuario.
- [ ] Validar estados `WATCHING`, `COMPLETED`, `ON_HOLD`, `DROPPED`, `PLAN_TO_WATCH`.
- [ ] Validar episodios vistos.
- [ ] Validar calificación personal.
- [ ] Validar fechas.

### Frontend

- [ ] Crear página de biblioteca.
- [ ] Crear filtros por estado.
- [ ] Crear formulario para agregar a biblioteca desde detalle.
- [ ] Crear edición rápida de estado.
- [ ] Crear edición de episodios vistos.
- [ ] Crear edición de calificación y notas.
- [ ] Crear acción eliminar de biblioteca.

### Testing y Calidad

- [ ] Probar agregar anime.
- [ ] Probar anime duplicado.
- [ ] Probar cambio de estado.
- [ ] Probar episodios inválidos.
- [ ] Probar eliminación.

### Documentación

- [ ] Revisar [[Endpoints - Biblioteca]].
- [ ] Revisar [[Reglas de Negocio]].
- [ ] Actualizar DB docs si cambia el schema.

### Criterio de Cierre

- [ ] Usuario administra biblioteca completa.
- [ ] Reglas de negocio se aplican en backend.

## Sprint 7 - Favoritos

Objetivo: permitir marcar anime como favoritos y mostrarlos en perfil.

Entregable: sistema de favoritos funcional.

### Backend

- [ ] Implementar `GET /api/favorites`.
- [ ] Implementar `POST /api/favorites`.
- [ ] Implementar `DELETE /api/favorites/:id`.
- [ ] Evitar favoritos duplicados.
- [ ] Persistir anime si se marca favorito y no existe localmente.

### Frontend

- [ ] Crear botón marcar favorito en detalle.
- [ ] Crear botón quitar favorito.
- [ ] Crear sección/lista de favoritos.
- [ ] Mostrar favoritos en perfil público.
- [ ] Mostrar estado visual de favorito.

### Testing y Calidad

- [ ] Probar agregar favorito.
- [ ] Probar favorito duplicado.
- [ ] Probar eliminar favorito.
- [ ] Probar favoritos en perfil público.

### Documentación

- [ ] Revisar [[Endpoints - Favoritos]].
- [ ] Revisar [[Reglas de Negocio#RN-14 Favorito Único]].

### Criterio de Cierre

- [ ] Usuario puede gestionar favoritos.
- [ ] Perfil público muestra favoritos.

## Sprint 8 - Estadísticas y Dashboard

Objetivo: entregar estadísticas útiles y dashboard personal.

Entregable: panel de usuario con resumen de actividad.

### Backend

- [ ] Implementar `GET /api/statistics/me`.
- [ ] Implementar `GET /api/statistics/users/:username`.
- [ ] Calcular total de anime.
- [ ] Calcular anime completados.
- [ ] Calcular episodios vistos.
- [ ] Calcular promedio de calificaciones.
- [ ] Calcular géneros principales.
- [ ] Calcular distribución por estado.

### Frontend

- [ ] Crear dashboard.
- [ ] Crear cards de estadísticas.
- [ ] Crear visualización por estados.
- [ ] Crear sección de anime en progreso.
- [ ] Crear sección de favoritos recientes.
- [ ] Crear estados vacíos para usuarios nuevos.

### Testing y Calidad

- [ ] Probar estadísticas sin datos.
- [ ] Probar estadísticas con biblioteca variada.
- [ ] Probar estadísticas públicas.

### Documentación

- [ ] Revisar [[Endpoints - Estadísticas]].
- [ ] Revisar [[Requisitos Funcionales#RF-12 Estadísticas Personales]].

### Criterio de Cierre

- [ ] Dashboard muestra datos reales.
- [ ] Estadísticas públicas y privadas funcionan.

## Sprint 9 - UX, Calidad Visual y Accesibilidad

Objetivo: elevar el producto a una experiencia visual profesional y no genérica.

Entregable: interfaz pulida, responsive y coherente.

### Frontend

- [ ] Definir dirección visual del producto.
- [ ] Revisar tipografía, espaciado y jerarquía.
- [ ] Mejorar navegación principal.
- [ ] Mejorar responsive mobile.
- [ ] Añadir skeleton loaders.
- [ ] Añadir estados vacíos cuidados.
- [ ] Añadir estados de error útiles.
- [ ] Mejorar feedback en formularios.
- [ ] Revisar contraste y foco visible.
- [ ] Revisar accesibilidad básica con teclado.

### Backend

- [ ] Revisar mensajes de error para frontend.
- [ ] Revisar consistencia de respuestas.

### Testing y Calidad

- [ ] Probar flujo completo en desktop.
- [ ] Probar flujo completo en mobile.
- [ ] Probar estados de loading/error/empty.
- [ ] Ejecutar lint/build.

### Documentación

- [ ] Actualizar [[Frontend]] si cambian patrones de UI.
- [ ] Actualizar screenshots si ya existen.

### Criterio de Cierre

- [ ] La app se siente consistente y presentable para portafolio.
- [ ] La app funciona correctamente en mobile.

## Sprint 10 - Testing Profesional

Objetivo: asegurar flujos críticos con pruebas y validaciones automatizadas.

Entregable: suite mínima de pruebas y scripts confiables.

### Backend

- [ ] Configurar framework de testing backend.
- [ ] Probar autenticación.
- [ ] Probar usuarios/perfil.
- [ ] Probar biblioteca.
- [ ] Probar favoritos.
- [ ] Probar estadísticas.
- [ ] Probar middlewares de auth y errores.

### Frontend

- [ ] Configurar testing frontend mínimo.
- [ ] Probar render de páginas críticas.
- [ ] Probar formularios principales.
- [ ] Probar estados de carga/error.

### Calidad

- [ ] Crear script `lint`.
- [ ] Crear script `test`.
- [ ] Crear script `build`.
- [ ] Ejecutar lint completo.
- [ ] Ejecutar tests completos.
- [ ] Ejecutar build frontend.
- [ ] Ejecutar build backend si aplica.

### Documentación

- [ ] Documentar estrategia de pruebas.
- [ ] Actualizar README cuando exista.

### Criterio de Cierre

- [ ] Scripts de calidad funcionan localmente.
- [ ] Flujos críticos tienen cobertura mínima.

## Sprint 11 - Deploy

Objetivo: publicar AnimeTracker para acceso público.

Entregable: frontend, backend y base de datos desplegados.

### Backend

- [ ] Preparar backend para producción.
- [ ] Configurar variables de entorno.
- [ ] Configurar CORS producción.
- [ ] Configurar migraciones en producción.
- [ ] Desplegar en Render o Railway.

### Frontend

- [ ] Preparar variables de entorno frontend.
- [ ] Configurar URL del backend.
- [ ] Desplegar en Vercel.
- [ ] Validar rutas públicas y privadas.

### Base de Datos

- [ ] Provisionar PostgreSQL en Neon, Railway o Render.
- [ ] Ejecutar migraciones.
- [ ] Validar conexión desde backend.

### Testing y Calidad

- [ ] Validar registro en producción.
- [ ] Validar login en producción.
- [ ] Validar búsqueda de anime.
- [ ] Validar biblioteca.
- [ ] Validar favoritos.
- [ ] Validar estadísticas.

### Documentación

- [ ] Actualizar [[Despliegue]].
- [ ] Documentar variables reales requeridas sin secretos.
- [ ] Documentar pasos de deploy.

### Criterio de Cierre

- [ ] App accesible desde Internet.
- [ ] Flujos principales funcionan en producción.

## Sprint 12 - CI/CD y Portafolio

Objetivo: cerrar el proyecto con automatización y presentación profesional.

Entregable: pipeline CI/CD funcional y documentación lista para portafolio.

### CI/CD

- [ ] Crear workflow de GitHub Actions.
- [ ] Ejecutar instalación de dependencias.
- [ ] Ejecutar lint backend.
- [ ] Ejecutar lint frontend.
- [ ] Ejecutar tests backend.
- [ ] Ejecutar tests frontend.
- [ ] Validar build frontend.
- [ ] Validar build backend.
- [ ] Configurar despliegue automático si aplica.
- [ ] Proteger rama principal.
- [ ] Ejecutar pipeline en pull request.
- [ ] Ejecutar pipeline en push a main.

### Portafolio

- [ ] Crear README profesional.
- [ ] Añadir descripción del problema.
- [ ] Añadir stack técnico.
- [ ] Añadir capturas de pantalla.
- [ ] Añadir diagrama de arquitectura.
- [ ] Añadir diagrama ER.
- [ ] Añadir guía de instalación.
- [ ] Añadir guía de despliegue.
- [ ] Añadir enlaces a demo.
- [ ] Añadir lista de funcionalidades.

### Documentación

- [ ] Revisar documentación completa en Obsidian.
- [ ] Actualizar [[Roadmap de Desarrollo]].
- [ ] Actualizar [[Despliegue]].
- [ ] Actualizar [[API REST]] si cambió algo.
- [ ] Marcar MVP como completado cuando aplique.

### Criterio de Cierre

- [ ] Pipeline CI/CD valida el proyecto.
- [ ] README está listo para reclutadores.
- [ ] Demo pública funciona.
- [ ] Documentación está sincronizada con el producto final.

## Backlog Post-MVP

- [ ] Google OAuth.
- [ ] Comentarios generales por anime.
- [ ] Seguidores.
- [ ] Notificaciones.
- [ ] Comentarios por episodio.
- [ ] Reseñas por episodio.
- [ ] Aplicación PWA.
- [ ] Panel administrativo avanzado.
- [ ] Recomendaciones personalizadas.
- [ ] Integración con AniList GraphQL.

## Referencias Relacionadas

- [[Roadmap de Desarrollo]]
- [[MVP]]
- [[Funcionalidades Futuras]]
- [[API REST]]
- [[Despliegue]]
