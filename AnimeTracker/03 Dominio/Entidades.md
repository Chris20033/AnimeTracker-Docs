---
title: Entidades
tags:
  - animetracker/dominio
  - animetracker/entidades
estado: migrado
fuente:
  - 4_Entidades.docx
---

# Entidades

## Usuario

Representa a una persona registrada dentro de la plataforma.

Responsabilidades:

- Autenticarse en el sistema.
- Gestionar su perfil.
- Gestionar su biblioteca de anime.
- Registrar favoritos.
- Consultar estadísticas.

Relaciones:

- Tiene un rol.
- Posee una biblioteca personal.
- Puede registrar múltiples anime.
- Puede marcar múltiples favoritos.
- Puede generar estadísticas asociadas a su actividad.

## Anime

Representa un anime disponible para consulta dentro de la plataforma.

Responsabilidades:

- Almacenar información general del anime.
- Servir como referencia para bibliotecas personales.
- Asociarse a géneros.

Relaciones:

- Puede pertenecer a múltiples géneros.
- Puede estar en múltiples bibliotecas.
- Puede ser marcado como favorito por múltiples usuarios.
- Puede tener comentarios generales.
- Puede tener episodios.

## Género

Representa una categoría temática asociada a un anime.

Ejemplos:

- Action.
- Adventure.
- Comedy.
- Drama.
- Fantasy.
- Romance.

Relaciones:

- Un género puede estar asociado a múltiples anime.
- Un anime puede poseer múltiples géneros.

## Biblioteca

Representa la colección personal de anime administrada por un usuario.

Responsabilidades:

- Mantener seguimiento de visualización.
- Registrar progreso.
- Almacenar calificaciones personales.

Relaciones:

- Pertenece a un usuario.
- Contiene múltiples registros de anime.

## Registro de Biblioteca

Representa la relación entre un usuario y un anime específico.

Responsabilidades:

- Registrar estado de visualización.
- Registrar episodios vistos.
- Registrar calificación personal.
- Registrar fechas de seguimiento.
- Registrar notas personales.

Relaciones:

- Pertenece a un usuario.
- Referencia un anime.

## Favorito

Representa un anime marcado como favorito por un usuario.

Relaciones:

- Pertenece a un usuario.
- Referencia un anime.

## Rol

Representa los permisos asignados a un usuario.

Tipos iniciales:

- `USER`
- `ADMIN`

Relaciones:

- Un rol puede estar asociado a múltiples usuarios.
- Un usuario posee un único rol.

## Recuperación de Contraseña

Representa una solicitud temporal para restablecer credenciales de acceso.

Responsabilidades:

- Generar tokens de recuperación.
- Controlar expiración de enlaces.
- Permitir restablecimiento seguro de contraseñas.

Relaciones:

- Está asociada a un usuario.

## Autenticación Externa

Representa proveedores externos usados para autenticación.

Proveedor inicial:

- Google.

Responsabilidades:

- Vincular cuentas externas con usuarios internos.
- Gestionar autenticación federada.

Relaciones:

- Está asociada a un usuario.

## Comentario de Anime

Representa un comentario realizado por un usuario en la página general de un anime.

Responsabilidades:

- Permitir opiniones generales sobre un anime.
- Mostrar comentarios públicos asociados a un anime.
- Registrar autor, contenido y fecha de publicación.

Relaciones:

- Pertenece a un usuario.
- Pertenece a un anime.

## Episodio

Representa un episodio individual perteneciente a un anime.

Responsabilidades:

- Almacenar número de episodio.
- Almacenar título del episodio cuando esté disponible.
- Servir como referencia para reseñas y comentarios por episodio.

Relaciones:

- Pertenece a un anime.
- Puede tener múltiples comentarios.
- Puede tener múltiples reseñas.

## Comentario de Episodio

Representa un comentario realizado por un usuario en un episodio específico.

Responsabilidades:

- Permitir discusión por episodio.
- Asociar comentarios a un episodio concreto.
- Registrar autor, contenido y fecha de publicación.

Relaciones:

- Pertenece a un usuario.
- Pertenece a un episodio.

## Reseña de Episodio

Representa una opinión estructurada sobre un episodio específico.

Responsabilidades:

- Permitir escribir una reseña.
- Permitir asignar una calificación individual al episodio.
- Registrar contenido, calificación y fecha de publicación.

Relaciones:

- Pertenece a un usuario.
- Pertenece a un episodio.

## Seguimiento de Usuario

Representa la relación social entre dos usuarios.

Responsabilidades:

- Permitir que un usuario siga a otro.
- Facilitar futuras funcionalidades sociales.
- Servir como base para notificaciones relacionadas con actividad de usuarios seguidos.

Relaciones:

- Un usuario puede seguir a múltiples usuarios.
- Un usuario puede ser seguido por múltiples usuarios.

## Notificación

Representa un aviso generado por el sistema hacia un usuario.

Responsabilidades:

- Informar sobre eventos relevantes.
- Servir como base para notificaciones web o PWA.
- Registrar estado de lectura.

Eventos posibles:

- Nuevo seguidor.
- Respuesta a comentario.
- Reacción a reseña.
- Actualización relevante del sistema.

Relaciones:

- Pertenece a un usuario receptor.
- Puede relacionarse con otro usuario, anime, episodio o comentario.

## Referencias Relacionadas

- [[Modelo Conceptual]]
- [[Diseño Lógico]]
- [[Reglas de Negocio]]
