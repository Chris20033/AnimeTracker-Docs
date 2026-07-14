---
title: Endpoints - Autenticación
tags:
  - animetracker/api
  - animetracker/auth
estado: inicial
---

# Endpoints - Autenticación

Ruta base:

```text
/api/auth
```

## POST /api/auth/register

Registra un nuevo usuario.

Autenticación: no requiere.

Body:

```json
{
  "username": "string",
  "email": "user@example.com",
  "password": "string"
}
```

Respuesta `201 Created`:

```json
{
  "data": {
    "user": {
      "id": "uuid",
      "username": "string",
      "email": "user@example.com",
      "role": "USER",
      "avatarUrl": null,
      "bannerUrl": null,
      "bio": null
    },
    "accessToken": "jwt"
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `409 USERNAME_ALREADY_EXISTS`
- `409 EMAIL_ALREADY_EXISTS`

Reglas relacionadas:

- [[Reglas de Negocio#RN-01 Username Único]]
- [[Reglas de Negocio#RN-02 Correo Electrónico Único]]
- [[Reglas de Negocio#RN-03 Longitud Mínima de Contraseña]]
- [[Reglas de Negocio#RN-26 Rol por Defecto]]

## POST /api/auth/login

Inicia sesión con email y contraseña.

Autenticación: no requiere.

Body:

```json
{
  "email": "user@example.com",
  "password": "string"
}
```

Respuesta `200 OK`:

```json
{
  "data": {
    "user": {
      "id": "uuid",
      "username": "string",
      "email": "user@example.com",
      "role": "USER",
      "avatarUrl": "string|null",
      "bannerUrl": "string|null",
      "bio": "string|null"
    },
    "accessToken": "jwt"
  }
}
```

Errores:

- `400 VALIDATION_ERROR`
- `401 AUTH_INVALID_CREDENTIALS`
- `403 FORBIDDEN` si el usuario está bloqueado o inactivo.

Reglas relacionadas:

- [[Reglas de Negocio#RN-04 Usuario Activo]]

## POST /api/auth/logout

Cierra sesión desde el cliente.

Autenticación: requiere JWT.

Respuesta `204 No Content`.

> [!note]
> En el MVP, si no existe blacklist de tokens, el logout consiste en eliminar el token del cliente.

## POST /api/auth/forgot-password

Solicita recuperación de contraseña.

Autenticación: no requiere.

Body:

```json
{
  "email": "user@example.com"
}
```

Respuesta `200 OK`:

```json
{
  "data": null,
  "message": "If the email exists, a recovery link will be sent"
}
```

Errores:

- `400 VALIDATION_ERROR`

> [!important]
> Para evitar enumeración de usuarios, la respuesta pública no debe revelar si el correo existe.

## POST /api/auth/reset-password

Restablece la contraseña usando token temporal.

Autenticación: no requiere.

Body:

```json
{
  "token": "string",
  "newPassword": "string"
}
```

Respuesta `200 OK`:

```json
{
  "data": null,
  "message": "Password updated successfully"
}
```

Errores:

- `400 VALIDATION_ERROR`
- `400 PASSWORD_RESET_TOKEN_INVALID`
- `400 PASSWORD_RESET_TOKEN_EXPIRED`

Reglas relacionadas:

- [[Reglas de Negocio#RN-06 Recuperación de Contraseña]]

## POST /api/auth/google

Inicio de sesión con Google.

Estado: post-MVP.

No implementar sin cambio explícito de alcance.

## Referencias Relacionadas

- [[Autenticación y Seguridad]]
- [[Flujos de Autenticación]]
- [[Requisitos Funcionales#RF-01 Registro de Usuario]]
- [[Requisitos Funcionales#RF-02 Inicio de Sesión]]
- [[Requisitos Funcionales#RF-16 Recuperación de Contraseña]]
