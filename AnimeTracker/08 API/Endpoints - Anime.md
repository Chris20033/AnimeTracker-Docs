---
title: Endpoints - Anime
tags:
  - animetracker/api
  - animetracker/anime
estado: inicial
---

# Endpoints - Anime

Ruta base:

```text
/api/anime
```

## GET /api/anime/search

Busca anime usando la API externa.

Autenticación: requiere JWT para MVP.

Query:

- `q`: texto de búsqueda, requerido.
- `page`: número de página, opcional.
- `limit`: cantidad por página, opcional.

Respuesta `200 OK`:

```json
{
  "data": [
    {
      "externalId": "string",
      "source": "JIKAN",
      "title": "string",
      "imageUrl": "string|null",
      "type": "TV",
      "year": 2024,
      "status": "Finished Airing",
      "score": 8.5
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 100,
    "totalPages": 5
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `401 AUTH_TOKEN_REQUIRED`
- `500 INTERNAL_SERVER_ERROR` si falla la API externa.

## GET /api/anime/:source/:externalId

Obtiene detalle de anime desde fuente externa o caché local.

Autenticación: requiere JWT para MVP.

Params:

- `source`: proveedor externo, ejemplo `JIKAN`.
- `externalId`: identificador externo.

Respuesta `200 OK`:

```json
{
  "data": {
    "externalId": "string",
    "source": "JIKAN",
    "title": "string",
    "titleEnglish": "string|null",
    "synopsis": "string|null",
    "imageUrl": "string|null",
    "episodes": 12,
    "duration": "24 min per ep",
    "status": "Finished Airing",
    "type": "TV",
    "season": "spring",
    "year": 2024,
    "score": 8.5,
    "genres": ["Action", "Fantasy"],
    "studio": "string|null",
    "airedFrom": "date|null"
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `401 AUTH_TOKEN_REQUIRED`
- `404 RESOURCE_NOT_FOUND`

## Referencias Relacionadas

- [[Requisitos Funcionales#RF-06 Búsqueda de Anime]]
- [[Requisitos Funcionales#RF-07 Consulta de Detalle de Anime]]
- [[Integraciones Externas]]
