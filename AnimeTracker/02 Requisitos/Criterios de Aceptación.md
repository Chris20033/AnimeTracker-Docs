---
title: Criterios de Aceptación
tags:
  - animetracker/requisitos
  - animetracker/qa
estado: creado
fuente:
  - 2_Requisitos.docx
---

# Criterios de Aceptación

## Autenticación

- Un usuario puede registrarse con username, email y contraseña válidos.
- No se permite registrar usernames duplicados.
- No se permite registrar emails duplicados.
- No se permite registrar contraseñas de menos de ocho caracteres.
- Un usuario puede iniciar sesión con credenciales válidas.
- Un usuario con credenciales inválidas recibe un error claro.
- Al iniciar sesión se genera un JWT.
- Al cerrar sesión, el cliente deja de enviar el token.

## Perfil

- Un usuario autenticado puede consultar su perfil.
- Un usuario autenticado puede actualizar username, avatar, banner y biografía.
- El perfil público muestra username, avatar, biografía, favoritos y estadísticas visibles.
- No se puede actualizar el username a uno ya existente.

## Anime

- Un usuario puede buscar anime usando la API externa.
- Los resultados muestran título, imagen, tipo, año, estado y score.
- Un usuario puede abrir el detalle de un anime.
- El detalle muestra sinopsis, episodios, duración, géneros, estudio, fecha, estado y score.

## Biblioteca

- Un usuario puede agregar un anime a su biblioteca.
- Un usuario no puede duplicar el mismo anime en su biblioteca.
- Un usuario puede actualizar estado, episodios vistos, calificación, fechas y notas.
- Los episodios vistos no pueden ser negativos.
- Los episodios vistos no pueden superar el total de episodios si el total está disponible.
- Un usuario puede eliminar un anime de su biblioteca sin eliminar el anime global.

## Favoritos

- Un usuario puede marcar anime como favorito.
- Un usuario puede quitar anime de favoritos.
- Un usuario no puede marcar dos veces el mismo anime como favorito.
- Los favoritos se muestran en el perfil público.

## Estadísticas

- El sistema muestra total de anime registrados.
- El sistema muestra total de anime completados.
- El sistema muestra total de episodios vistos.
- El sistema muestra promedio de calificaciones.
- El sistema muestra géneros más vistos.
- El sistema muestra distribución por estado.

## Administración

- Solo un usuario `ADMIN` puede acceder al panel administrativo.
- Un administrador puede consultar usuarios registrados.
- Un administrador puede bloquear usuarios.
- Un usuario bloqueado no puede iniciar sesión.

## Referencias Relacionadas

- [[Requisitos Funcionales]]
- [[Reglas de Negocio]]
- [[Casos de Uso]]
