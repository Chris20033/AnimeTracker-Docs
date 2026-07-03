---
title: Usuarios y Roles
tags:
  - animetracker/producto
  - animetracker/roles
estado: migrado
fuente:
  - 1_Planeacion_AnimeTracker.docx
  - 2_Requisitos.docx
  - 3_Casos_de_Uso.docx
---

# Usuarios y Roles

AnimeTracker contempla tres tipos de actor a nivel funcional y dos roles internos iniciales.

## Actores del Sistema

### Usuario No Autenticado

Visitante que accede a la plataforma sin iniciar sesión.

Puede:

- Registrarse.
- Iniciar sesión.
- Iniciar sesión con Google cuando esté disponible.
- Solicitar recuperación de contraseña.
- Consultar perfiles públicos si la funcionalidad está expuesta públicamente.

### Usuario Autenticado

Usuario registrado que inició sesión correctamente.

Puede:

- Gestionar su perfil.
- Buscar anime.
- Consultar detalles de anime.
- Crear y actualizar su biblioteca.
- Marcar favoritos.
- Ver estadísticas personales.
- Consultar perfiles públicos.
- Cerrar sesión.

### Administrador

Usuario con permisos especiales para supervisar la plataforma.

Puede:

- Consultar usuarios registrados.
- Bloquear usuarios.
- Consultar estadísticas generales del sistema.

## Roles Internos

### USER

Rol por defecto de todo usuario registrado.

Permisos principales:

- Gestionar perfil.
- Buscar anime.
- Administrar biblioteca.
- Marcar favoritos.
- Ver estadísticas.
- Consultar perfiles públicos.

### ADMIN

Rol administrativo.

Permisos principales:

- Consultar usuarios.
- Bloquear usuarios.
- Revisar estadísticas generales.
- Moderar contenido cuando existan comentarios o reseñas.

## Reglas Asociadas

- Todo usuario nuevo inicia con rol `USER`.
- Solo usuarios `ADMIN` pueden acceder a funciones administrativas.
- Un usuario bloqueado o inactivo no puede iniciar sesión.

## Referencias Relacionadas

- [[Casos de Uso]]
- [[Reglas de Negocio]]
- [[Autenticación y Seguridad]]
