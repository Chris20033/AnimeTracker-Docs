---
title: Diccionario de Datos
tags:
  - animetracker/base-de-datos
  - animetracker/diccionario-datos
estado: creado
fuente:
  - 5_Diseño_logico_base_de_datos.docx
---

# Diccionario de Datos

Este diccionario resume tablas, propósito y restricciones principales.

## users

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| username | Nombre público único | Único, requerido |
| email | Correo del usuario | Único, requerido |
| password_hash | Contraseña hasheada | Nullable si usa OAuth |
| avatar_url | Avatar del perfil | Opcional |
| banner_url | Imagen de portada | Opcional |
| bio | Biografía | Opcional |
| role | Rol del usuario | `USER` o `ADMIN` |
| is_active | Estado de acceso | Boolean |
| created_at | Fecha de creación | Requerido |
| updated_at | Fecha de actualización | Requerido |

## external_auth_accounts

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| user_id | Usuario asociado | FK users.id |
| provider | Proveedor externo | Ejemplo: `GOOGLE` |
| provider_user_id | ID del usuario en proveedor | Único por proveedor |
| created_at | Fecha de vinculación | Requerido |

## password_reset_tokens

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| user_id | Usuario asociado | FK users.id |
| token | Token seguro | Requerido, no reutilizable |
| expires_at | Expiración | Requerido |
| used_at | Fecha de uso | Nullable |
| created_at | Fecha de creación | Requerido |

## anime

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| external_id | ID en API externa | Único con `source` |
| title | Título principal | Requerido |
| title_english | Título inglés | Opcional |
| alternative_titles | Variantes de título devueltas por Kitsu | Array de texto, default `[]` |
| search_text | Texto normalizado para búsqueda local por títulos | Texto, default `""` |
| synopsis | Sinopsis | Opcional |
| image_url | Imagen principal | Opcional |
| episodes | Total de episodios | Opcional |
| duration | Duración por episodio | Opcional |
| status | Estado de emisión | Opcional |
| type | Tipo de anime | Opcional |
| season | Temporada | Opcional |
| year | Año | Opcional |
| score | Score externo | Opcional |
| source | API origen | Requerido |
| created_at | Fecha de creación | Requerido |
| updated_at | Fecha de actualización | Requerido |

## genres

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| name | Nombre del género | Único, requerido |

## anime_genres

| Campo | Propósito | Restricciones |
|---|---|---|
| anime_id | Anime asociado | FK anime.id |
| genre_id | Género asociado | FK genres.id |

Restricción recomendada: índice único compuesto `anime_id + genre_id`.

## user_anime_list

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| user_id | Usuario dueño | FK users.id |
| anime_id | Anime asociado | FK anime.id |
| status | Estado de visualización | Enum requerido |
| episodes_watched | Progreso | Entero >= 0 |
| personal_score | Calificación personal | 1 a 10, opcional |
| notes | Notas personales | Opcional |
| started_at | Fecha de inicio | Opcional |
| finished_at | Fecha de finalización | Opcional |
| created_at | Fecha de creación | Requerido |
| updated_at | Fecha de actualización | Requerido |

Restricción recomendada: índice único compuesto `user_id + anime_id`.

## favorites

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| user_id | Usuario dueño | FK users.id |
| anime_id | Anime favorito | FK anime.id |
| created_at | Fecha de creación | Requerido |

Restricción recomendada: índice único compuesto `user_id + anime_id`.

## anime_comments

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| user_id | Autor | FK users.id |
| anime_id | Anime comentado | FK anime.id |
| content | Contenido | Requerido, no vacío |
| is_deleted | Borrado lógico | Boolean |
| created_at | Fecha de creación | Requerido |
| updated_at | Fecha de actualización | Requerido |

## follows

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| follower_id | Usuario que sigue | FK users.id |
| following_id | Usuario seguido | FK users.id |
| created_at | Fecha de creación | Requerido |

Restricciones recomendadas:

- `follower_id != following_id`.
- Índice único compuesto `follower_id + following_id`.

## notifications

| Campo | Propósito | Restricciones |
|---|---|---|
| id | Identificador interno | PK |
| user_id | Usuario receptor | FK users.id |
| type | Tipo de notificación | Enum requerido |
| title | Título | Requerido |
| message | Mensaje | Requerido |
| is_read | Estado de lectura | Boolean |
| created_at | Fecha de creación | Requerido |

## Referencias Relacionadas

- [[Diseño Lógico]]
- [[Diagrama ER]]
- [[Reglas de Negocio]]
