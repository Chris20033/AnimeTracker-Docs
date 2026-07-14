---
title: Decisiones y Supuestos
tags:
  - animetracker/inicio
  - animetracker/decisiones
estado: creado
---

# Decisiones y Supuestos

Este documento registra ajustes realizados durante la migración desde `.docx` a Obsidian.

## Normalización de Estados

Los documentos originales usan variantes como `Plan to Watch`, `Plan ToWatch` y `Plan To Watch`.

Decisión: usar enums internos consistentes:

- `WATCHING`
- `COMPLETED`
- `ON_HOLD`
- `DROPPED`
- `PLAN_TO_WATCH`

En UI se pueden mostrar como:

- Viendo.
- Completado.
- En pausa.
- Abandonado.
- Planeado.

## Separación MVP y Post-MVP

Algunas funcionalidades aparecen mezcladas entre documentos. Para mantener un alcance realista:

- Google OAuth se clasifica como post-MVP recomendado.
- Comentarios, seguidores y notificaciones se clasifican como post-MVP.
- El panel administrativo avanzado se clasifica como post-MVP.
- El MVP conserva autenticación básica, recuperación de contraseña, perfil, búsqueda, biblioteca, favoritos, estadísticas y deploy.

## Biblioteca Como Concepto

Conceptualmente existe una biblioteca del usuario.

En base de datos no se crea tabla `biblioteca`; la tabla `user_anime_list` representa directamente los registros de la biblioteca.

## API Externa

Se usa Kitsu API como proveedor externo activo para búsqueda, catálogo, detalle y home.

AniList GraphQL queda como mejora futura.

## Persistencia de Anime

No se almacena todo el catálogo externo.

Solo se persisten anime consultados o asociados a usuarios mediante biblioteca, favoritos o comentarios.

## Documentos Originales

Los `.docx` originales se mantienen intactos como fuente histórica.

## Referencias Relacionadas

- [[Alcance y MVP]]
- [[Reglas de Negocio]]
- [[Diseño Lógico]]
- [[Integraciones Externas]]
