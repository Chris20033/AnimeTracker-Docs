---
title: Convenciones de Respuesta
tags:
  - animetracker/api
estado: inicial
---

# Convenciones de Respuesta

## Respuesta Exitosa Simple

```json
{
  "data": {},
  "message": "Operation completed successfully"
}
```

## Respuesta Exitosa con Lista

```json
{
  "data": [],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 100,
    "totalPages": 5
  }
}
```

## Respuesta de Error

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid request data",
    "details": []
  }
}
```

## Fechas

Las fechas deben enviarse en formato ISO 8601.

Ejemplo:

```json
{
  "createdAt": "2026-06-24T10:00:00.000Z"
}
```

## Nombres de Campos

La API debe exponer JSON en `camelCase`.

Ejemplos:

- `passwordHash` no debe exponerse.
- `avatarUrl`.
- `bannerUrl`.
- `episodesWatched`.
- `personalScore`.

## Campos Sensibles

Nunca exponer:

- `passwordHash`.
- Tokens de recuperación.
- Secretos OAuth.
- Variables de entorno.

## Referencias Relacionadas

- [[API REST]]
- [[Errores y Códigos HTTP]]
