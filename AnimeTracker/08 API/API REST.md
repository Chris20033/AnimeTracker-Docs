---
title: API REST
tags:
  - animetracker/api
  - animetracker/backend
estado: inicial
---

# API REST

La API REST de AnimeTracker expone las funcionalidades del backend para el frontend React.

## Base Path

```text
/api
```

## Grupos de Endpoints

| Grupo | Ruta base | Documento |
|---|---|---|
| Autenticación | `/api/auth` | [[Endpoints - Autenticación]] |
| Usuarios | `/api/users` | [[Endpoints - Usuarios]] |
| Anime | `/api/anime` | [[Endpoints - Anime]] |
| Home | `/api/home` | [[Endpoints - Home]] |
| Biblioteca | `/api/library` | [[Endpoints - Biblioteca]] |
| Favoritos | `/api/favorites` | [[Endpoints - Favoritos]] |
| Estadísticas | `/api/statistics` | [[Endpoints - Estadísticas]] |
| Administración | `/api/admin` | [[Endpoints - Administración]] |

## Autenticación

Las rutas privadas usan JWT enviado en el header:

```http
Authorization: Bearer <token>
```

## Convenciones

- Las respuestas exitosas deben seguir [[Convenciones de Respuesta]].
- Los errores deben seguir [[Errores y Códigos HTTP]].
- Los datos de entrada deben validarse con Zod.
- La lógica de negocio debe vivir en services.
- El acceso a datos debe pasar por repositories y Prisma.

## Alcance MVP

Endpoints necesarios para MVP:

- Registro, login, logout lógico y recuperación de contraseña.
- Perfil privado y perfil público.
- Home pública con contenido dinámico.
- Búsqueda y detalle de anime.
- Biblioteca personal.
- Favoritos.
- Estadísticas básicas.

## Post-MVP

No implementar sin cambio explícito de alcance:

- Google OAuth.
- Comentarios.
- Seguidores.
- Notificaciones.
- PWA.
- Recomendaciones.
- Administración avanzada.

## Referencias Relacionadas

- [[Backend]]
- [[Autenticación y Seguridad]]
- [[Requisitos Funcionales]]
- [[Reglas de Negocio]]
