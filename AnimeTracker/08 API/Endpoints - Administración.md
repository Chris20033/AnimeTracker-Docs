---
title: Endpoints - Administración
tags:
  - animetracker/api
  - animetracker/admin
estado: inicial
---

# Endpoints - Administración

Ruta base:

```text
/api/admin
```

Todos los endpoints requieren JWT y rol `ADMIN`.

> [!warning]
> La administración básica existe en requisitos, pero el panel administrativo avanzado es post-MVP. Implementar solo lo mínimo cuando sea necesario.

## GET /api/admin/users

Lista usuarios registrados.

Autenticación: requiere JWT.

Rol: `ADMIN`.

Query opcional:

- `page`.
- `limit`.
- `search`.
- `isActive`.

Respuesta `200 OK`:

```json
{
  "data": [
    {
      "id": "uuid",
      "username": "string",
      "email": "user@example.com",
      "role": "USER",
      "isActive": true,
      "createdAt": "datetime"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 1,
    "totalPages": 1
  }
}
```

Errores:

- `401 AUTH_TOKEN_REQUIRED`
- `403 FORBIDDEN`

## PATCH /api/admin/users/:id/status

Activa o bloquea un usuario.

Autenticación: requiere JWT.

Rol: `ADMIN`.

Body:

```json
{
  "isActive": false
}
```

Respuesta `200 OK`:

```json
{
  "data": {
    "id": "uuid",
    "username": "string",
    "isActive": false
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `401 AUTH_TOKEN_REQUIRED`
- `403 FORBIDDEN`
- `404 RESOURCE_NOT_FOUND`

## GET /api/admin/statistics

Obtiene estadísticas generales del sistema.

Autenticación: requiere JWT.

Rol: `ADMIN`.

Respuesta `200 OK`:

```json
{
  "data": {
    "totalUsers": 0,
    "activeUsers": 0,
    "totalAnimeStored": 0,
    "totalLibraryEntries": 0,
    "totalFavorites": 0
  }
}
```

Errores:

- `401 AUTH_TOKEN_REQUIRED`
- `403 FORBIDDEN`

## Reglas Relacionadas

- [[Reglas de Negocio#RN-27 Gestión Administrativa]]
- [[Reglas de Negocio#RN-28 Bloqueo de Usuarios]]
