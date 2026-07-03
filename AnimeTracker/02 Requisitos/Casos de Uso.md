---
title: Casos de Uso
tags:
  - animetracker/requisitos
  - animetracker/casos-de-uso
estado: migrado
fuente:
  - 3_Casos_de_Uso.docx
---

# Casos de Uso

Los casos de uso describen las interacciones principales entre los actores y AnimeTracker.

## Actores

- Usuario no autenticado.
- Usuario autenticado.
- Administrador.

## Usuario No Autenticado

### CU-01 Registrarse

Permite a un visitante crear una cuenta.

Flujo principal:

1. El usuario accede al formulario de registro.
2. Ingresa username, correo electrónico y contraseña.
3. El sistema valida la información.
4. El sistema crea la cuenta.
5. El usuario puede iniciar sesión.

Resultado esperado: el usuario queda registrado correctamente.

### CU-02 Iniciar Sesión

Permite acceder mediante correo electrónico y contraseña.

Resultado esperado: el usuario accede a funcionalidades privadas.

### CU-03 Iniciar Sesión con Google

Permite autenticarse con una cuenta de Google.

Resultado esperado: el usuario accede sin contraseña local.

> [!info]
> Clasificado como post-MVP.

### CU-04 Recuperar Contraseña

Permite recuperar acceso mediante enlace enviado por correo electrónico.

Resultado esperado: el usuario establece nueva contraseña y recupera acceso.

## Usuario Autenticado

### CU-05 Gestionar Perfil

Permite modificar información personal.

Acciones disponibles:

- Actualizar avatar.
- Actualizar imagen de portada.
- Modificar biografía.
- Modificar username.

### CU-06 Buscar Anime

Permite buscar anime desde una API externa.

Resultado esperado: el sistema muestra resultados coincidentes.

### CU-07 Consultar Información de Anime

Permite visualizar detalle completo de un anime.

Resultado esperado: el usuario consulta la información completa del anime seleccionado.

### CU-08 Agregar Anime a Biblioteca

Permite incorporar un anime a la biblioteca personal.

Resultado esperado: el anime queda asociado al usuario con estado de visualización.

### CU-09 Actualizar Progreso de Visualización

Permite modificar estado y progreso de un anime registrado.

Acciones disponibles:

- Actualizar estado.
- Actualizar episodios vistos.
- Registrar calificación.
- Registrar notas personales.

### CU-10 Eliminar Anime de Biblioteca

Permite retirar un anime de la biblioteca personal.

Resultado esperado: el anime deja de estar asociado al usuario.

### CU-11 Gestionar Favoritos

Permite marcar y desmarcar anime como favoritos.

Resultado esperado: los favoritos aparecen en el perfil público y privado.

### CU-12 Consultar Estadísticas Personales

Permite visualizar estadísticas generadas a partir de la actividad del usuario.

Resultado esperado: el usuario obtiene información sobre sus hábitos de visualización.

### CU-13 Consultar Perfil Público de Otro Usuario

Permite visualizar información pública de otros usuarios registrados.

Resultado esperado: el usuario puede consultar perfiles públicos y estadísticas visibles.

### CU-14 Cerrar Sesión

Permite finalizar la sesión actual.

Resultado esperado: el usuario abandona las áreas protegidas.

## Administrador

### CU-15 Consultar Usuarios Registrados

Permite visualizar los usuarios registrados.

### CU-16 Bloquear Usuarios

Permite restringir temporal o permanentemente el acceso de un usuario.

### CU-17 Consultar Estadísticas Generales

Permite visualizar métricas globales relacionadas con el uso de la plataforma.

## Referencias Relacionadas

- [[Casos de Uso - Vista General]]
- [[Usuarios y Roles]]
- [[Requisitos Funcionales]]
