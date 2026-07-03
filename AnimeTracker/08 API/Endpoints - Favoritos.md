---
title: Endpoints - Favoritos
tags:
  - animetracker/api
  - animetracker/favoritos
estado: inicial
---

# Endpoints - Favoritos

Ruta base:

```text
/api/favorites
```

Todos los endpoints requieren JWT.

## GET /api/favorites

Lista los favoritos del usuario autenticado.

Respuesta `200 OK`:

```json
{
  "data": [
    {
      "id": "uuid",
      "createdAt": "datetime",
      "anime": {
        "id": "uuid",
        "externalId": "string",
        "source": "JIKAN",
        "title": "string",
        "imageUrl": "string|null"
      }
    }
  ]
}
```

## POST /api/favorites

Marca un anime como favorito.

Body:

```json
{
  "source": "JIKAN",
  "externalId": "string"
}
```

Respuesta `201 Created`:

```json
{
  "data": {
    "id": "uuid",
    "createdAt": "datetime",
    "anime": {
      "id": "uuid",
      "externalId": "string",
      "source": "JIKAN",
      "title": "string"
    }
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `409 FAVORITE_ALREADY_EXISTS`

## DELETE /api/favorites/:id

Quita un anime de favoritos.

Respuesta `204 No Content`.

Errores:

- `404 RESOURCE_NOT_FOUND`

## Reglas Relacionadas

- [[Reglas de Negocio#RN-14 Favorito Único]]
- [[Reglas de Negocio#RN-15 Existencia Previa]]
