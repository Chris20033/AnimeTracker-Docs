---
title: Reglas de Negocio
tags:
  - animetracker/dominio
  - animetracker/reglas
estado: migrado
fuente:
  - 6_Reglas_de_Negocio.docx
---

# Reglas de Negocio

Las reglas de negocio definen restricciones, validaciones y comportamientos que deben cumplirse para garantizar integridad y funcionamiento correcto.

## Usuarios

### RN-01 Username Único

Cada usuario debe poseer un username único.

### RN-02 Correo Electrónico Único

Cada usuario debe poseer un correo electrónico único.

### RN-03 Longitud Mínima de Contraseña

Las contraseñas registradas manualmente deben contener al menos ocho caracteres.

### RN-04 Usuario Activo

Únicamente los usuarios activos pueden iniciar sesión.

Los usuarios bloqueados o desactivados no pueden acceder a la plataforma.

### RN-05 Integridad de Perfil

Un usuario debe poseer obligatoriamente:

- Username.
- Correo electrónico.

Los demás campos son opcionales.

## Autenticación

### RN-06 Recuperación de Contraseña

Los enlaces de recuperación deben tener fecha de expiración y no pueden reutilizarse.

### RN-07 Inicio de Sesión Mediante Google

Si un usuario inicia sesión mediante Google y el correo ya existe, ambas cuentas deben vincularse automáticamente sin generar duplicados.

## Biblioteca de Anime

### RN-08 Registro Único por Anime

Un usuario no puede registrar el mismo anime más de una vez dentro de su biblioteca.

### RN-09 Estados Permitidos

Los estados válidos para un anime en biblioteca son:

- `WATCHING`
- `COMPLETED`
- `ON_HOLD`
- `DROPPED`
- `PLAN_TO_WATCH`

> [!note]
> Se normalizan los estados internos a formato enum. En la interfaz pueden mostrarse como Viendo, Completado, En pausa, Abandonado y Planeado.

### RN-10 Episodios Vistos Válidos

La cantidad de episodios vistos no puede ser negativa.

Si el total de episodios está disponible, episodios vistos no debe superar ese total.

### RN-11 Finalización Automática

Cuando el usuario registre todos los episodios disponibles, puede marcar el anime como completado.

Durante el MVP el sistema no realizará este cambio automáticamente.

### RN-12 Calificación Personal

La calificación personal debe estar dentro del rango definido por la plataforma.

Rango inicial:

- Mínimo: 1.
- Máximo: 10.

### RN-13 Eliminación de Anime

Al eliminar un anime de la biblioteca personal, solo se elimina la relación con el usuario.

La información general del anime permanece almacenada.

## Favoritos

### RN-14 Favorito Único

Un usuario no puede marcar el mismo anime como favorito más de una vez.

### RN-15 Existencia Previa

Un anime debe existir dentro del sistema antes de poder ser marcado como favorito.

## Comentarios

### RN-16 Comentarios Asociados

Todo comentario debe estar asociado a un usuario existente y a un anime existente.

### RN-17 Comentarios Vacíos

No se permite publicar comentarios vacíos.

### RN-18 Edición de Comentarios

Únicamente el autor del comentario puede editarlo.

### RN-19 Eliminación de Comentarios

Únicamente el autor o un administrador pueden eliminar un comentario.

Para conservar historial, los comentarios pueden marcarse como eliminados lógicamente.

## Seguidores

### RN-20 Auto Seguimiento

Un usuario no puede seguirse a sí mismo.

### RN-21 Relación Única

Un usuario no puede seguir dos veces al mismo usuario.

### RN-22 Eliminación de Seguimiento

Un usuario puede dejar de seguir a otro usuario en cualquier momento.

## Notificaciones

### RN-23 Usuario Receptor

Toda notificación debe estar asociada a un usuario receptor válido.

### RN-24 Estado de Lectura

Las notificaciones deben poder marcarse como leídas.

### RN-25 Conservación de Historial

Las notificaciones permanecen almacenadas hasta definir una política de limpieza.

## Roles y Administración

### RN-26 Rol por Defecto

Todo usuario registrado tendrá inicialmente el rol `USER`.

### RN-27 Gestión Administrativa

Solo usuarios con rol `ADMIN` pueden acceder a funciones administrativas.

### RN-28 Bloqueo de Usuarios

Un administrador puede bloquear usuarios.

Los usuarios bloqueados pierden acceso hasta ser reactivados.

## Integridad General

### RN-29 Fechas Válidas

La fecha de finalización de un anime no puede ser anterior a la fecha de inicio.

### RN-30 Relaciones Consistentes

No deben existir registros huérfanos.

Toda relación debe apuntar a entidades válidas.

### RN-31 Auditoría Temporal

Las entidades principales deben almacenar fechas de creación y actualización.

## Referencias Relacionadas

- [[Requisitos Funcionales]]
- [[Diseño Lógico]]
- [[Diccionario de Datos]]
