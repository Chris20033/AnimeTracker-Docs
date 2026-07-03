---
title: Modelo Conceptual
tags:
  - animetracker/dominio
  - animetracker/modelo-conceptual
estado: migrado
fuente:
  - 4_Entidades.docx
---

# Modelo Conceptual

El modelo conceptual describe las entidades principales del dominio AnimeTracker y sus relaciones antes de transformarlas en tablas de base de datos.

## Entidades Núcleo

- [[Entidades#Usuario|Usuario]]
- [[Entidades#Anime|Anime]]
- [[Entidades#Género|Género]]
- [[Entidades#Biblioteca|Biblioteca]]
- [[Entidades#Registro de Biblioteca|Registro de Biblioteca]]
- [[Entidades#Favorito|Favorito]]
- [[Entidades#Rol|Rol]]

## Entidades de Autenticación

- [[Entidades#Recuperación de Contraseña|Recuperación de Contraseña]]
- [[Entidades#Autenticación Externa|Autenticación Externa]]

## Entidades Sociales y Futuras

- [[Entidades#Comentario de Anime|Comentario de Anime]]
- [[Entidades#Episodio|Episodio]]
- [[Entidades#Comentario de Episodio|Comentario de Episodio]]
- [[Entidades#Reseña de Episodio|Reseña de Episodio]]
- [[Entidades#Seguimiento de Usuario|Seguimiento de Usuario]]
- [[Entidades#Notificación|Notificación]]

## Relaciones Principales

- Un usuario posee una biblioteca personal.
- Un usuario puede tener múltiples anime registrados.
- Un usuario puede marcar múltiples anime como favoritos.
- Un anime puede pertenecer a múltiples géneros.
- Un anime puede estar presente en bibliotecas de múltiples usuarios.
- Un usuario tiene un rol.
- Un usuario puede tener tokens de recuperación de contraseña.
- Un usuario puede tener cuentas externas asociadas.
- Un usuario puede escribir comentarios.
- Un usuario puede seguir a otros usuarios.
- Un usuario puede recibir notificaciones.

## Decisión de Diseño

> [!important]
> En el diseño lógico no se necesita una tabla `biblioteca` separada si `user_anime_list` representa directamente la relación entre usuario y anime. Conceptualmente sí puede hablarse de biblioteca como colección personal.

## Referencias Relacionadas

- [[Entidades]]
- [[Diseño Lógico]]
- [[Diagrama ER]]
