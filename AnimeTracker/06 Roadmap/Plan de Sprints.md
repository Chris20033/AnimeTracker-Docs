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

- [x] Implementar `GET /api/users/me`.
- [x] Implementar `PATCH /api/users/me`.
- [x] Implementar `GET /api/users/:username`.
- [x] Implementar Cloudinary para procesar imagenes.
- [x] Validar username único al editar.
- [x] Evitar exponer campos sensibles.


### Frontend

- [x] Crear página de perfil privado.
- [x] Crear formulario de edición.
- [x] Crear página de perfil público.
- [x] Mostrar avatar, banner, username y biografía.
- [x] Preparar secciones para favoritos y estadísticas públicas.

### Testing y Calidad

- [x] Probar consulta de perfil privado.
- [x] Probar actualización de perfil.
- [x] Probar username duplicado.
- [x] Probar perfil público inexistente.

### Documentación

- [x] Revisar [[Endpoints - Usuarios]].
- [x] Revisar [[Requisitos Funcionales#RF-04 Gestión de Perfil]].
- [x] Revisar [[Requisitos Funcionales#RF-05 Perfil Público]].

### Criterio de Cierre

- [x] Usuario edita su perfil.
- [x] Perfil público es visible por username.
- [x] No se exponen datos sensibles.

## Sprint 5 - Anime Search y Detail

Objetivo: integrar búsqueda y detalle de anime usando una API externa desde backend.

Entregable: usuario puede buscar anime y consultar detalle.

### Backend

- [x] Crear cliente para Kitsu API.
- [x] Migrar proveedor activo de anime a Kitsu API.
- [x] Implementar `GET /api/anime/search`.
- [x] Implementar `GET /api/anime/:source/:externalId`.
- [x] Normalizar respuesta externa.
- [x] Manejar errores de API externa.
- [x] Implementar paginación.

### Frontend

- [x] Crear página de inicio estilo MyAnimeList
- [x] Crear página de búsqueda.
- [x] Crear campo de búsqueda.
- [x] Crear lista/grid de resultados.
- [x] Crear página de detalle.
- [x] Mostrar imagen, título, sinopsis, episodios, géneros, score y estado.
- [x] Implementar loading/error/empty states.
- [x] Implementar paginación.

### Testing y Calidad

- [x] Probar búsqueda con resultados.
- [x] Probar búsqueda sin resultados.
- [x] Probar detalle válido.
- [x] Probar fallo de API externa.

### Documentación

- [x] Revisar [[Endpoints - Anime]].
- [x] Revisar [[Integraciones Externas]].

### Extra - Home dinámica backend

- [x] Hacer pública la búsqueda de anime.
- [x] Hacer público el detalle de anime.
- [x] Implementar `GET /api/home`.
- [x] Implementar `GET /api/home/featured`.
- [x] Implementar `GET /api/home/top-airing`.
- [x] Implementar `GET /api/home/seasonal`.
- [x] Implementar `GET /api/home/upcoming`.
- [x] Implementar `GET /api/home/popular`.
- [x] Implementar `GET /api/home/recommendations`.
- [x] Normalizar datos para hero, carruseles y recomendaciones.
- [x] Documentar endpoints de home en Swagger.
- [x] Verificar endpoints públicos sin JWT.

### Extra - Home dinámica Frontend
- [x] Conectar backend con frontend.
- [x] Crear componente de carrusel para mostrar contenido

### Extra - Catálogo de Anime backend
- [x] Implementar `GET /api/anime/catalog`.
- [x] Implementar filtros públicos de catálogo.
- [x] Implementar `GET /api/anime/genres`.
- [x] Documentar catálogo en Swagger.
- [x] Verificar catálogo público sin JWT.

### Extra - Catálogo de Anime Frontend
- [x] Conectar `GET /api/anime/catalog`.
- [x] Conectar `GET /api/anime/genres`.
- [x] Convertir `/anime` en catálogo público.
- [x] Mantener búsqueda mediante query `q`.
- [x] Implementar filtros públicos de catálogo.
- [x] Mantener paginación y cache con TanStack Query.

### Criterio de Cierre

- [x] Usuario busca anime.
- [x] Usuario abre detalle.
- [x] Frontend no consume la API externa directamente.

### Extra - Migración Anime API a Kitsu

- [x] Crear cliente Kitsu.
- [x] Migrar búsqueda a Kitsu.
- [x] Migrar catálogo a Kitsu.
- [x] Migrar detalle a Kitsu.
- [x] Migrar home dinámica a Kitsu.
- [x] Migrar géneros a categorías Kitsu.
- [x] Actualizar Swagger.
- [x] Verificar endpoints públicos sin JWT.

## Sprint 6 - Biblioteca Personal

Objetivo: implementar la funcionalidad principal de seguimiento de anime.

Entregable: usuario puede administrar su biblioteca personal.

### Backend

- [x] Implementar `GET /api/library`.
- [x] Implementar `POST /api/library`.
- [x] Implementar `PATCH /api/library/:id`.
- [x] Implementar `DELETE /api/library/:id`.
- [x] Persistir anime al agregarlo si no existe.
- [x] Validar anime duplicado por usuario.
- [x] Validar estados `WATCHING`, `COMPLETED`, `ON_HOLD`, `DROPPED`, `PLAN_TO_WATCH`.
- [x] Validar episodios vistos.
- [x] Validar calificación personal.
- [x] Validar fechas.

### Frontend

- [x] Crear página de biblioteca.
- [x] Crear filtros por estado.
- [x] Crear formulario para agregar a biblioteca desde detalle.
- [x] Crear edición rápida de estado.
- [x] Crear edición de episodios vistos.
- [x] Crear edición de calificación y notas.
- [x] Crear acción eliminar de biblioteca.
- [x] Crear búsqueda por título en biblioteca.

### Extra - Frontend

- [x] Arreglar bug carrusel.
- [x] Agregar paginación numérica en catálogo.
### Testing y Calidad

- [ ] Probar agregar anime.
- [ ] Probar anime duplicado.
- [ ] Probar cambio de estado.
- [ ] Probar episodios inválidos.
- [ ] Probar eliminación.

### Documentación

- [x] Revisar [[Endpoints - Biblioteca]].
- [ ] Revisar [[Reglas de Negocio]].
- [x] Actualizar DB docs si cambia el schema.

### Criterio de Cierre

- [ ] Usuario administra biblioteca completa.
- [ ] Reglas de negocio se aplican en backend.

## Sprint 7 - Favoritos

Objetivo: permitir marcar anime como favoritos y mostrarlos en perfil.

Entregable: sistema de favoritos funcional.

### Backend

- [x] Implementar `GET /api/favorites`.
- [x] Implementar `POST /api/favorites`.
- [x] Implementar `DELETE /api/favorites/:id`.
- [x] Evitar favoritos duplicados.
- [x] Persistir anime si se marca favorito y no existe localmente.

### Frontend

- [x] Crear botón marcar favorito en detalle.
- [x] Crear botón quitar favorito.
- [x] Crear sección/lista de favoritos.
- [x] Mostrar favoritos en perfil público.
- [x] Mostrar estado visual de favorito.

### Extra - Frontend

- [x] Optimizar carga inicial con lazy loading por rutas en `AppRouter`.
- [x] Agregar fallback accesible para carga de páginas bajo demanda.
- [x] Restaurar scroll al inicio al cambiar de página en catálogo y biblioteca.
- [x] Pulir listas de favoritos para perfiles con muchas entradas.

### Testing y Calidad

- [x] Probar agregar favorito.
- [x] Probar favorito duplicado.
- [x] Probar eliminar favorito.
- [x] Probar favoritos en perfil público.

### Documentación

- [x] Revisar [[Endpoints - Favoritos]].
- [x] Revisar [[Reglas de Negocio#RN-14 Favorito Único]].

### Criterio de Cierre

- [x] Usuario puede gestionar favoritos.
- [x] Perfil público muestra favoritos.

## Sprint 8 - Estadísticas y Dashboard

Objetivo: entregar estadísticas útiles y dashboard personal.

Entregable: panel de usuario con resumen de actividad.

### Backend

- [x] Implementar `GET /api/statistics/me`.
- [x] Implementar `GET /api/statistics/users/:username`.
- [x] Calcular total de anime.
- [x] Calcular anime completados.
- [x] Calcular episodios vistos.
- [x] Calcular promedio de calificaciones.
- [x] Calcular géneros principales.
- [x] Calcular distribución por estado.

### Frontend

- [x] Crear dashboard.
- [x] Crear cards de estadísticas.
- [x] Crear visualización por estados.
- [x] Crear sección de anime en progreso.
- [x] Crear sección de favoritos recientes.
- [x] Crear estados vacíos para usuarios nuevos.

### Testing y Calidad

- [x] Probar estadísticas sin datos.
- [x] Probar estadísticas con biblioteca variada.
- [x] Probar estadísticas públicas.

### Documentación

- [x] Revisar [[Endpoints - Estadísticas]].
- [x] Revisar [[Requisitos Funcionales#RF-12 Estadísticas Personales]].

### Criterio de Cierre

- [x] Dashboard muestra datos reales.
- [x] Estadísticas públicas y privadas funcionan.

## Sprint 9 - UX, Calidad Visual y Accesibilidad

Objetivo: elevar el producto a una experiencia visual profesional y no genérica.

Entregable: interfaz pulida, responsive y coherente.

### Frontend

- [x] Definir dirección visual del producto.
- [x] Revisar tipografía, espaciado y jerarquía.
- [x] Mejorar navegación principal.
- [x] Mejorar responsive mobile.
- [x] Añadir skeleton loaders.
- [x] Añadir estados vacíos cuidados.
- [x] Añadir estados de error útiles.
- [x] Mejorar feedback en formularios.
- [x] Revisar contraste y foco visible.
- [x] Revisar accesibilidad básica con teclado.

### Backend

- [x] Revisar mensajes de error para frontend.
- [x] Revisar consistencia de respuestas.

### Testing y Calidad

- [x] Probar flujo completo en desktop.
- [x] Probar flujo completo en mobile.
- [x] Probar estados de loading/error/empty.
- [x] Ejecutar lint/build.

### Documentación

- [x] Actualizar [[Frontend]] si cambian patrones de UI.
- [ ] Actualizar screenshots si ya existen.

### Criterio de Cierre

- [x] La app se siente consistente y presentable para portafolio.
- [x] La app funciona correctamente en mobile.

## Sprint 10 - Testing Profesional

Objetivo: asegurar flujos críticos con pruebas y validaciones automatizadas.

Entregable: suite mínima de pruebas y scripts confiables.

### Backend

- [x] Configurar Vitest y Supertest.
- [x] Probar autenticación.
- [x] Probar usuarios y perfil.
- [x] Probar biblioteca.
- [x] Probar favoritos.
- [x] Probar estadísticas.
- [x] Probar validaciones (Zod).
- [x] Probar middlewares (auth, upload y manejo de errores).

### Frontend

- [x] Configurar Vitest y React Testing Library.
- [x] Probar páginas principales.
- [x] Probar componentes principales.
- [x] Probar formularios.
- [x] Probar estados de carga, éxito y error.

### Opcional

- [x] Configurar Playwright para pruebas End-to-End.
- [x] Probar flujo completo de la aplicación (login → búsqueda → biblioteca → favoritos).

### Calidad

- [x] Crear script `lint`.
- [x] Crear script `test`.
- [x] Crear script `build`.
- [x] Ejecutar lint completo.
- [x] Ejecutar tests completos.
- [x] Ejecutar build frontend.
- [ ] Ejecutar build backend si aplica.

### Documentación

- [x] Documentar estrategia de pruebas.
- [ ] Actualizar README cuando exista.

### Criterio de Cierre

- [x] Scripts de calidad funcionan localmente.
- [x] Flujos críticos tienen cobertura mínima.

## Sprint 11 - Deploy

Objetivo: publicar AnimeTracker para acceso público.

Entregable: frontend, backend y base de datos desplegados.

### Backend

- [x] Preparar backend para producción.
- [x] Configurar variables de entorno.
- [x] Configurar CORS producción.
- [x] Configurar migraciones en producción.
- [x] Desplegar en Render o Railway.

### Frontend

- [x] Preparar variables de entorno frontend.
- [x] Configurar URL del backend.
- [x] Desplegar en Vercel.
- [x] Validar rutas públicas y privadas.

### Base de Datos

- [x] Provisionar PostgreSQL en Neon, Railway o Render.
- [x] Ejecutar migraciones.
- [x] Validar conexión desde backend.

### Testing y Calidad

- [x] Validar registro en producción.
- [x] Validar login en producción.
- [x] Validar búsqueda de anime.
- [x] Validar biblioteca.
- [x] Validar favoritos.
- [x] Validar estadísticas.

### Documentación

- [x] Actualizar [[Despliegue]].
- [x] Documentar variables reales requeridas sin secretos.
- [x] Documentar pasos de deploy.

### Criterio de Cierre

- [x] App accesible desde Internet.
- [x] Flujos principales funcionan en producción.

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

- [x] Crear README profesional.
- [x] Añadir descripción del problema.
- [x] Añadir stack técnico.
- [x] Añadir capturas de pantalla.
- [x] Añadir diagrama de arquitectura.
- [x] Añadir diagrama ER.
- [x] Añadir guía de instalación.
- [x] Añadir guía de despliegue.
- [x] Añadir enlaces a demo.
- [x] Añadir lista de funcionalidades.

### Documentación

- [x] Revisar documentación completa en Obsidian.
- [x] Actualizar [[Roadmap de Desarrollo]].
- [x] Actualizar [[Despliegue]].
- [x] Actualizar [[API REST]] si cambió algo.
- [x] Marcar MVP como completado cuando aplique.

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
- [ ] Integrar múltiples lenguajes.

## Referencias Relacionadas

- [[Roadmap de Desarrollo]]
- [[MVP]]
- [[Funcionalidades Futuras]]
- [[API REST]]
- [[Despliegue]]
