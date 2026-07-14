---
title: Glosario
tags:
  - animetracker/inicio
  - animetracker/glosario
estado: creado
---

# Glosario

## AnimeTracker

Aplicación web Full Stack para gestionar biblioteca personal de anime, progreso, favoritos y estadísticas.

## Biblioteca

Colección personal de anime de un usuario. En base de datos se representa con `user_anime_list`.

## Estado de Visualización

Estado que describe la relación del usuario con un anime.

Valores internos normalizados:

- `WATCHING`: Viendo.
- `COMPLETED`: Completado.
- `ON_HOLD`: En pausa.
- `DROPPED`: Abandonado.
- `PLAN_TO_WATCH`: Planeado.

## Favorito

Anime marcado por un usuario como destacado. Puede mostrarse en el perfil público.

## Kitsu API

API externa usada como proveedor activo de anime para búsqueda, catálogo, detalle y contenido de home.

## JWT

Token usado para autenticar peticiones protegidas entre frontend y backend.

## MVP

Producto Mínimo Viable. Versión funcional mínima para validar y mostrar el proyecto.

## Prisma

ORM usado para modelar y consultar PostgreSQL desde el backend.

## Perfil Público

Vista visible de un usuario con información limitada como username, avatar, biografía, favoritos y estadísticas generales.

## Referencias Relacionadas

- [[Visión del Producto]]
- [[Alcance y MVP]]
- [[Diseño Lógico]]
