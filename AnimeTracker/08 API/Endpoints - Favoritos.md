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
        "source": "KITSU",
        "title": "string",
        "titleEnglish": "string|null",
        "alternativeTitles": [],
        "imageUrl": "string|null",
        "type": "string|null",
        "year": 2020,
        "status": "string|null",
        "score": 8.5
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
  "source": "KITSU",
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
        "source": "KITSU",
        "title": "string",
        "titleEnglish": "string|null",
        "alternativeTitles": [],
        "imageUrl": "string|null"
      }
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `401 AUTH_TOKEN_REQUIRED` o `AUTH_TOKEN_INVALID`
- `409 FAVORITE_ALREADY_EXISTS`
- `503 EXTERNAL_ANIME_API_ERROR` si falla Kitsu al persistir el anime.

Uso frontend:

- El detalle de anime y las cards de biblioteca muestran una estrella rellena/vacía para marcar o quitar favoritos.
- La lista privada de favoritos se muestra en el perfil privado.
- El perfil público muestra los favoritos visibles del usuario.

## DELETE /api/favorites/:id

Quita un anime de favoritos.

Respuesta `204 No Content`.

Errores:

- `404 RESOURCE_NOT_FOUND`
- `401 AUTH_TOKEN_REQUIRED` o `AUTH_TOKEN_INVALID`

## Reglas Relacionadas

- [[Reglas de Negocio#RN-14 Favorito Único]]
- [[Reglas de Negocio#RN-15 Existencia Previa]]
