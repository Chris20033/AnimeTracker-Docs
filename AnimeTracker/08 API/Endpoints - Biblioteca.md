---
title: Endpoints - Biblioteca
tags:
  - animetracker/api
  - animetracker/biblioteca
estado: inicial
---

# Endpoints - Biblioteca

Ruta base:

```text
/api/library
```

Todos los endpoints requieren JWT.

## GET /api/library

Lista la biblioteca del usuario autenticado.

Query opcional:

- `status`: `WATCHING`, `COMPLETED`, `ON_HOLD`, `DROPPED`, `PLAN_TO_WATCH`.
- `q`: texto de búsqueda en títulos guardados del anime. Busca por título canónico, inglés, romanizado, japonés y abreviados cuando Kitsu los devuelve.
- `page`.
- `limit`.

Respuesta `200 OK`:

```json
{
  "data": [
    {
      "id": "uuid",
      "status": "WATCHING",
      "episodesWatched": 3,
      "personalScore": 8,
      "notes": "string|null",
      "startedAt": "date|null",
      "finishedAt": "date|null",
      "anime": {
        "id": "uuid",
        "externalId": "string",
        "source": "KITSU",
        "title": "string",
        "titleEnglish": "string|null",
        "alternativeTitles": ["string"],
        "imageUrl": "string|null",
        "episodes": 12
      }
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

## POST /api/library

Agrega un anime a la biblioteca.

Body:

```json
{
  "source": "KITSU",
  "externalId": "string",
  "status": "PLAN_TO_WATCH"
}
```

Respuesta `201 Created`:

```json
{
  "data": {
    "id": "uuid",
    "status": "PLAN_TO_WATCH",
    "episodesWatched": 0,
    "personalScore": null,
    "anime": {
      "id": "uuid",
      "externalId": "string",
      "source": "KITSU",
      "title": "string"
    }
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `401 AUTH_TOKEN_REQUIRED` o `AUTH_TOKEN_INVALID`
- `409 ANIME_ALREADY_IN_LIBRARY`
- `503 EXTERNAL_ANIME_API_ERROR` si falla Kitsu al persistir el anime.

## PATCH /api/library/:id

Actualiza un registro de biblioteca.

Body:

```json
{
  "status": "WATCHING",
  "episodesWatched": 4,
  "personalScore": 8,
  "notes": "string|null",
  "startedAt": "date|null",
  "finishedAt": "date|null"
}
```

Respuesta `200 OK`:

```json
{
  "data": {
    "id": "uuid",
    "status": "WATCHING",
    "episodesWatched": 4,
    "personalScore": 8,
    "notes": "string|null",
    "startedAt": "date|null",
    "finishedAt": "date|null"
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `401 AUTH_TOKEN_REQUIRED` o `AUTH_TOKEN_INVALID`
- `404 RESOURCE_NOT_FOUND`
- `422 VALIDATION_ERROR` si episodios o fechas incumplen reglas.

Notas:

- `personalScore` acepta números enteros de `1` a `10` o `null` para dejar la entrada sin calificación personal.

## DELETE /api/library/:id

Elimina un anime de la biblioteca del usuario.

Respuesta `204 No Content`.

Errores:

- `401 AUTH_TOKEN_REQUIRED` o `AUTH_TOKEN_INVALID`
- `404 RESOURCE_NOT_FOUND`

## Reglas Relacionadas

- [[Reglas de Negocio#RN-08 Registro Único por Anime]]
- [[Reglas de Negocio#RN-09 Estados Permitidos]]
- [[Reglas de Negocio#RN-10 Episodios Vistos Válidos]]
- [[Reglas de Negocio#RN-12 Calificación Personal]]
- [[Reglas de Negocio#RN-13 Eliminación de Anime]]
- [[Reglas de Negocio#RN-29 Fechas Válidas]]
