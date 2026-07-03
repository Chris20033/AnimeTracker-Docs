---
title: Errores y Códigos HTTP
tags:
  - animetracker/api
estado: inicial
---

# Errores y Códigos HTTP

## Códigos HTTP

| Código | Uso |
|---|---|
| `200 OK` | Consulta o actualización exitosa |
| `201 Created` | Recurso creado |
| `204 No Content` | Eliminación exitosa sin cuerpo |
| `400 Bad Request` | Datos inválidos o regla de negocio incumplida |
| `401 Unauthorized` | Token ausente, inválido o expirado |
| `403 Forbidden` | Usuario autenticado sin permisos suficientes |
| `404 Not Found` | Recurso no encontrado |
| `409 Conflict` | Conflicto por unicidad o duplicados |
| `422 Unprocessable Entity` | Validación semántica fallida |
| `500 Internal Server Error` | Error inesperado |

## Códigos de Error Internos

| Código | Descripción |
|---|---|
| `VALIDATION_ERROR` | Datos de entrada inválidos |
| `AUTH_INVALID_CREDENTIALS` | Credenciales incorrectas |
| `AUTH_TOKEN_REQUIRED` | Falta token JWT |
| `AUTH_TOKEN_INVALID` | Token inválido o expirado |
| `FORBIDDEN` | Permisos insuficientes |
| `RESOURCE_NOT_FOUND` | Recurso no encontrado |
| `USERNAME_ALREADY_EXISTS` | Username duplicado |
| `EMAIL_ALREADY_EXISTS` | Email duplicado |
| `ANIME_ALREADY_IN_LIBRARY` | Anime duplicado en biblioteca |
| `FAVORITE_ALREADY_EXISTS` | Favorito duplicado |
| `PASSWORD_RESET_TOKEN_INVALID` | Token de recuperación inválido |
| `PASSWORD_RESET_TOKEN_EXPIRED` | Token de recuperación expirado |

## Formato de Error

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid request data",
    "details": [
      {
        "field": "email",
        "message": "Invalid email format"
      }
    ]
  }
}
```

## Referencias Relacionadas

- [[Convenciones de Respuesta]]
- [[API REST]]
