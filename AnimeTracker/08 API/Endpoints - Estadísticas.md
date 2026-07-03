---
title: Endpoints - Estadísticas
tags:
  - animetracker/api
  - animetracker/estadisticas
estado: inicial
---

# Endpoints - Estadísticas

Ruta base:

```text
/api/statistics
```

## GET /api/statistics/me

Obtiene estadísticas personales del usuario autenticado.

Autenticación: requiere JWT.

Respuesta `200 OK`:

```json
{
  "data": {
    "totalAnime": 0,
    "completedAnime": 0,
    "totalEpisodesWatched": 0,
    "averageScore": null,
    "topGenres": [
      {
        "name": "Action",
        "count": 0
      }
    ],
    "statusDistribution": {
      "WATCHING": 0,
      "COMPLETED": 0,
      "ON_HOLD": 0,
      "DROPPED": 0,
      "PLAN_TO_WATCH": 0
    }
  }
}
```

Errores:

- `401 AUTH_TOKEN_REQUIRED`
- `401 AUTH_TOKEN_INVALID`

## GET /api/statistics/users/:username

Obtiene estadísticas públicas de un usuario.

Autenticación: no requiere.

Params:

- `username`.

Respuesta `200 OK`:

```json
{
  "data": {
    "username": "string",
    "totalAnime": 0,
    "completedAnime": 0,
    "totalEpisodesWatched": 0,
    "averageScore": null,
    "topGenres": [],
    "statusDistribution": {
      "WATCHING": 0,
      "COMPLETED": 0,
      "ON_HOLD": 0,
      "DROPPED": 0,
      "PLAN_TO_WATCH": 0
    }
  }
}
```

Errores:

- `404 RESOURCE_NOT_FOUND`

## Referencias Relacionadas

- [[Requisitos Funcionales#RF-12 Estadísticas Personales]]
- [[Criterios de Aceptación#Estadísticas]]
