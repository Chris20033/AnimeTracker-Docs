---
title: Módulos Principales
tags:
  - animetracker/producto
  - animetracker/modulos
estado: migrado
fuente:
  - 1_Planeacion_AnimeTracker.docx
  - 7_Arquitectura_del_Sistema.docx
---

# Módulos Principales

## Autenticación

Incluye:

- Registro.
- Login.
- Logout.
- Protección de rutas.
- Hash de contraseñas.
- JWT access token.
- Recuperación de contraseña.
- Google OAuth como funcionalidad posterior al MVP.

## Usuarios

Incluye:

- Perfil privado.
- Perfil público.
- Avatar.
- Imagen de portada.
- Biografía.
- Username único.
- Estado activo o bloqueado.

## Anime

Incluye:

- Búsqueda externa.
- Detalle del anime.
- Géneros.
- Episodios.
- Imagen.
- Sinopsis.
- Score externo.
- Fuente de datos externa.

## Biblioteca

Incluye:

- Agregar anime.
- Cambiar estado.
- Actualizar episodios vistos.
- Calificar anime.
- Registrar notas personales.
- Registrar fechas de inicio y finalización.
- Eliminar anime de la biblioteca.

## Favoritos

Incluye:

- Marcar anime como favorito.
- Quitar anime de favoritos.
- Mostrar favoritos en perfil público.

## Estadísticas

Incluye:

- Total de animes registrados.
- Total de animes completados.
- Total de episodios vistos.
- Promedio de calificaciones.
- Géneros más vistos.
- Distribución por estado de visualización.

## Administración

Incluye:

- Consulta de usuarios registrados.
- Bloqueo de usuarios.
- Estadísticas generales del sistema.

> [!note]
> El módulo administrativo puede quedar reducido en el MVP y ampliarse en versiones posteriores.

## Comunidad y Social

Funcionalidades previstas para evolución del sistema:

- Comentarios generales por anime.
- Seguimiento entre usuarios.
- Notificaciones.
- Comentarios por episodio.
- Reseñas por episodio.

## Referencias Relacionadas

- [[Requisitos Funcionales]]
- [[Arquitectura del Sistema]]
- [[Roadmap de Desarrollo]]
