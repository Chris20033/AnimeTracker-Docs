---
title: Diseño Lógico
tags:
  - animetracker/base-de-datos
  - animetracker/diseno-logico
estado: migrado
fuente:
  - 5_Diseño_logico_base_de_datos.docx
---

# Diseño Lógico

El diseño lógico transforma el modelo conceptual en tablas, campos principales y relaciones para PostgreSQL usando Prisma como ORM.

## users

Almacena la información principal de los usuarios registrados.

Campos principales:

- `id`
- `username`
- `email`
- `password_hash`
- `avatar_url`
- `banner_url`
- `bio`
- `role`
- `is_active`
- `created_at`
- `updated_at`

Consideraciones:

- `username` debe ser único.
- `email` debe ser único.
- `password_hash` puede ser nulo si el usuario se registró mediante Google.
- `role` diferencia usuarios normales y administradores.

## external_auth_accounts

Almacena cuentas externas asociadas a un usuario.

Campos principales:

- `id`
- `user_id`
- `provider`
- `provider_user_id`
- `created_at`

Consideraciones:

- Un usuario puede tener una o varias cuentas externas.
- Para la primera versión extendida se considera Google.

## password_reset_tokens

Almacena tokens temporales para recuperación de contraseña.

Campos principales:

- `id`
- `user_id`
- `token`
- `expires_at`
- `used_at`
- `created_at`

Consideraciones:

- Cada token debe expirar.
- Un token usado no puede reutilizarse.
- El token debe almacenarse de forma segura.

## anime

Almacena información básica de anime consultados desde una API externa.

Campos principales:

- `id`
- `external_id`
- `title`
- `title_english`
- `synopsis`
- `image_url`
- `episodes`
- `duration`
- `status`
- `type`
- `season`
- `year`
- `score`
- `source`
- `created_at`
- `updated_at`

Consideraciones:

- `external_id` identifica el anime dentro de la API externa.
- No se almacenan todos los anime disponibles, solo los consultados o asociados por usuarios.
- `source` indica la API de origen.

## genres

Almacena géneros disponibles.

Campos principales:

- `id`
- `name`

Consideraciones:

- `name` debe ser único.

## anime_genres

Tabla intermedia para relación muchos a muchos entre anime y géneros.

Campos principales:

- `anime_id`
- `genre_id`

## user_anime_list

Representa la biblioteca personal de anime de cada usuario.

Campos principales:

- `id`
- `user_id`
- `anime_id`
- `status`
- `episodes_watched`
- `personal_score`
- `notes`
- `started_at`
- `finished_at`
- `created_at`
- `updated_at`

Estados permitidos:

- `WATCHING`
- `COMPLETED`
- `ON_HOLD`
- `DROPPED`
- `PLAN_TO_WATCH`

Consideraciones:

- Un usuario no puede tener el mismo anime duplicado.
- `episodes_watched` no debe superar el total de episodios disponible.
- `personal_score` es opcional.

## favorites

Almacena anime marcados como favoritos.

Campos principales:

- `id`
- `user_id`
- `anime_id`
- `created_at`

Consideraciones:

- Un usuario no puede marcar el mismo anime más de una vez.
- Los favoritos pueden mostrarse en el perfil público.

## anime_comments

Almacena comentarios generales en la página de un anime.

Campos principales:

- `id`
- `user_id`
- `anime_id`
- `content`
- `is_deleted`
- `created_at`
- `updated_at`

Consideraciones:

- Los comentarios se asocian a usuario y anime.
- `is_deleted` permite ocultar comentarios sin borrarlos físicamente.

## follows

Representa seguimiento entre usuarios.

Campos principales:

- `id`
- `follower_id`
- `following_id`
- `created_at`

Consideraciones:

- Un usuario puede seguir a múltiples usuarios.
- Un usuario puede ser seguido por múltiples usuarios.
- Un usuario no puede seguirse a sí mismo.
- No debe duplicarse la relación `follower_id` y `following_id`.

## notifications

Almacena notificaciones generadas para usuarios.

Campos principales:

- `id`
- `user_id`
- `type`
- `title`
- `message`
- `is_read`
- `created_at`

Tipos iniciales posibles:

- `NEW_FOLLOWER`
- `COMMENT_REPLY`
- `SYSTEM`

## Relaciones Principales

- Un usuario puede tener muchas cuentas externas.
- Un usuario puede tener muchos tokens de recuperación.
- Un usuario puede tener muchos anime en su biblioteca.
- Un anime puede estar en muchas bibliotecas.
- Un usuario puede marcar muchos anime como favoritos.
- Un anime puede ser favorito de muchos usuarios.
- Un anime puede pertenecer a muchos géneros.
- Un género puede pertenecer a muchos anime.
- Un usuario puede escribir muchos comentarios.
- Un anime puede tener muchos comentarios.
- Un usuario puede seguir a muchos usuarios.
- Un usuario puede ser seguido por muchos usuarios.
- Un usuario puede recibir muchas notificaciones.

## Referencias Relacionadas

- [[Diccionario de Datos]]
- [[Diagrama ER]]
- [[Reglas de Negocio]]
