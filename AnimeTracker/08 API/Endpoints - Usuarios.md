---
title: Endpoints - Usuarios
tags:
  - animetracker/api
  - animetracker/usuarios
estado: inicial
---

# Endpoints - Usuarios

Ruta base:

```text
/api/users
```

## GET /api/users/me

Obtiene el perfil privado del usuario autenticado.

Autenticación: requiere JWT.

Respuesta `200 OK`:

```json
{
  "data": {
    "id": "uuid",
    "username": "string",
    "email": "user@example.com",
    "role": "USER",
    "avatarUrl": "string|null",
    "bannerUrl": "string|null",
    "bio": "string|null",
    "createdAt": "datetime"
  }
}
```

Errores:

- `401 AUTH_TOKEN_REQUIRED`
- `401 AUTH_TOKEN_INVALID`

## PATCH /api/users/me

Actualiza el perfil privado.

Autenticación: requiere JWT.

Body:

```json
{
  "username": "string",
  "avatarUrl": "string|null",
  "bannerUrl": "string|null",
  "bio": "string|null"
}
```

Respuesta `200 OK`:

```json
{
  "data": {
    "id": "uuid",
    "username": "string",
    "email": "user@example.com",
    "avatarUrl": "string|null",
    "bannerUrl": "string|null",
    "bio": "string|null"
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `401 AUTH_TOKEN_REQUIRED`
- `409 USERNAME_ALREADY_EXISTS`

Reglas relacionadas:

- [[Reglas de Negocio#RN-01 Username Único]]
- [[Reglas de Negocio#RN-05 Integridad de Perfil]]

## GET /api/users/:username

Obtiene el perfil público de un usuario.

Autenticación: no requiere.

Params:

- `username`: username público.

Respuesta `200 OK`:

```json
{
  "data": {
    "id": "uuid",
    "username": "string",
    "avatarUrl": "string|null",
    "bannerUrl": "string|null",
    "bio": "string|null",
    "favorites": [],
    "statistics": {
      "totalAnime": 0,
      "completedAnime": 0,
      "totalEpisodesWatched": 0,
      "averageScore": null
    }
  }
}
```

Errores:

- `404 RESOURCE_NOT_FOUND`

## Referencias Relacionadas

- [[Requisitos Funcionales#RF-04 Gestión de Perfil]]
- [[Requisitos Funcionales#RF-05 Perfil Público]]
- [[Usuarios y Roles]]
