---
title: Endpoints - Home
tags:
  - animetracker/api
  - animetracker/home
estado: inicial
---

# Endpoints - Home

Ruta base:

```text
/api/home
```

Estos endpoints alimentan la página principal pública con información normalizada desde Kitsu API. No requieren autenticación.

## GET /api/home

Devuelve el contenido agregado para la home en una sola llamada.

Respuesta `200 OK`:

```json
{
  "data": {
    "hero": {
      "externalId": "string",
      "source": "KITSU",
      "title": "string",
      "imageUrl": "string|null",
      "type": "TV",
      "year": 2026,
      "status": "Currently Airing",
      "score": 8.9,
      "synopsis": "string|null",
      "episodes": 12,
      "genres": ["Action", "Fantasy"],
      "trailerUrl": "string|null",
      "rank": 1,
      "popularity": 20,
      "members": 250000
    },
    "sections": {
      "featured": [],
      "topAiring": [],
      "seasonal": [],
      "upcoming": [],
      "popular": [],
      "recommendations": []
    }
  }
}
```

Errores:

- `429 EXTERNAL_ANIME_API_RATE_LIMITED` si Kitsu aplica rate limit.
- `503 EXTERNAL_ANIME_API_ERROR` si falla temporalmente la API externa.

## Endpoints por sección

- `GET /api/home/featured`
- `GET /api/home/top-airing`
- `GET /api/home/seasonal`
- `GET /api/home/upcoming`
- `GET /api/home/popular`
- `GET /api/home/recommendations`

Todos devuelven:

```json
{
  "data": []
}
```

## Referencias Relacionadas

- [[API REST]]
- [[Endpoints - Anime]]
- [[Integraciones Externas]]
