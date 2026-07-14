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

Autenticación: pública.

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
      "source": "KITSU",
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
- `429 EXTERNAL_ANIME_API_RATE_LIMITED` si Kitsu aplica rate limit.
- `503 EXTERNAL_ANIME_API_ERROR` si falla temporalmente la API externa.

## GET /api/anime/catalog

Lista anime para la página de catálogo usando Kitsu API.

Autenticación: pública.

Query:

- `page`: número de página, opcional.
- `limit`: cantidad por página, opcional, máximo 25.
- `q`: texto de búsqueda, opcional. Kitsu busca por títulos conocidos del anime, incluyendo variantes en inglés, romanizadas y japonesas cuando existen.
- `type`: `tv`, `movie`, `ova`, `special`, `ona`, `music`, `cm`, `pv`, `tv_special`, opcional.
- `status`: `airing`, `current`, `complete`, `finished`, `upcoming`, opcional.
- `rating`: `g`, `pg`, `pg13`, `r17`, `r`, `rx`, `r18`, opcional.
- `genres`: lista de slugs de categorías separada por comas, opcional.
- `order_by`: `mal_id`, `title`, `start_date`, `end_date`, `episodes`, `score`, `scored_by`, `rank`, `popularity`, `members`, `favorites`, opcional.
- `sort`: `asc` o `desc`, opcional.

Respuesta `200 OK`:

```json
{
  "data": [
    {
      "externalId": "string",
      "source": "KITSU",
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
    "limit": 24,
    "total": 100,
    "totalPages": 5
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `429 EXTERNAL_ANIME_API_RATE_LIMITED` si Kitsu aplica rate limit.
- `503 EXTERNAL_ANIME_API_ERROR` si falla temporalmente la API externa.

## GET /api/anime/genres

Lista categorías de Kitsu para filtros del catálogo. El campo `id` corresponde al slug que debe enviarse en `genres`.

Autenticación: pública.

Respuesta `200 OK`:

```json
{
  "data": [
    {
      "id": "action",
      "externalId": "8",
      "name": "Action",
      "slug": "action",
      "count": 2441
    }
  ]
}
```

Errores:

- `429 EXTERNAL_ANIME_API_RATE_LIMITED` si Kitsu aplica rate limit.
- `503 EXTERNAL_ANIME_API_ERROR` si falla temporalmente la API externa.

## GET /api/anime/:source/:externalId

Obtiene detalle de anime desde fuente externa o caché local.

Autenticación: pública.

Params:

- `source`: proveedor externo, ejemplo `KITSU`.
- `externalId`: identificador externo numérico positivo.

Respuesta `200 OK`:

```json
{
  "data": {
    "externalId": "string",
    "source": "KITSU",
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
- `404 RESOURCE_NOT_FOUND`
- `429 EXTERNAL_ANIME_API_RATE_LIMITED` si Kitsu aplica rate limit.
- `503 EXTERNAL_ANIME_API_ERROR` si falla temporalmente la API externa.

## Referencias Relacionadas

- [[Requisitos Funcionales#RF-06 Búsqueda de Anime]]
- [[Requisitos Funcionales#RF-07 Consulta de Detalle de Anime]]
- [[Integraciones Externas]]
