---
title: Requisitos Funcionales
tags:
  - animetracker/requisitos
  - animetracker/funcional
estado: migrado
fuente:
  - 2_Requisitos.docx
---

# Requisitos Funcionales

## RF-01 Registro de Usuario

El sistema debe permitir que los usuarios creen una cuenta proporcionando username, correo electrónico y contraseña.

### Criterios de Aceptación

- El username debe ser único.
- El correo electrónico debe ser único.
- La contraseña debe tener mínimo ocho caracteres.
- El sistema debe mostrar errores cuando los datos no sean válidos.

## RF-02 Inicio de Sesión

El sistema debe permitir que usuarios registrados accedan mediante correo electrónico y contraseña.

### Criterios de Aceptación

- El sistema valida credenciales.
- Se genera un token JWT.
- El usuario es redirigido al dashboard después del login exitoso.

## RF-03 Cierre de Sesión

El sistema debe permitir cerrar sesión de forma segura.

### Criterios de Aceptación

- El token de autenticación deja de usarse en el cliente.
- El usuario es redirigido a la pantalla de inicio de sesión.

## RF-04 Gestión de Perfil

El sistema debe permitir consultar y modificar la información del perfil.

### Datos Editables

- Username.
- Avatar.
- Imagen de portada.
- Biografía.

## RF-05 Perfil Público

El sistema debe permitir visualizar perfiles de usuario públicamente.

### Información Mostrada

- Username.
- Avatar.
- Biografía.
- Animes favoritos.
- Estadísticas generales visibles.

## RF-06 Búsqueda de Anime

El sistema debe permitir buscar anime usando una API externa.

### Información en Resultados

- Título.
- Imagen.
- Tipo de anime.
- Año de emisión.
- Estado.
- Calificación general.

## RF-07 Consulta de Detalle de Anime

El sistema debe permitir consultar información detallada de un anime seleccionado.

### Información Mostrada

- Título.
- Sinopsis.
- Imagen principal.
- Número de episodios.
- Duración por episodio.
- Géneros.
- Estudio de animación.
- Fecha de estreno.
- Estado de emisión.
- Calificación general.

## RF-08 Agregar Anime a Biblioteca

El sistema debe permitir agregar anime a la biblioteca personal.

### Estados Disponibles

- `WATCHING`
- `COMPLETED`
- `ON_HOLD`
- `DROPPED`
- `PLAN_TO_WATCH`

## RF-09 Actualización de Biblioteca

El sistema debe permitir modificar información asociada a un anime dentro de la biblioteca personal.

### Información Editable

- Estado.
- Episodios vistos.
- Calificación personal.
- Fecha de inicio.
- Fecha de finalización.
- Notas personales.

## RF-10 Eliminación de Anime de Biblioteca

El sistema debe permitir eliminar anime de la biblioteca personal del usuario.

## RF-11 Gestión de Favoritos

El sistema debe permitir administrar una lista de anime favoritos.

### Funcionalidades

- Agregar favoritos.
- Eliminar favoritos.
- Visualizar favoritos.
- Mostrar favoritos en perfiles públicos.

## RF-12 Estadísticas Personales

El sistema debe generar estadísticas relacionadas con la actividad del usuario.

### Estadísticas Iniciales

- Total de anime registrados.
- Total de anime completados.
- Total de episodios vistos.
- Promedio de calificaciones otorgadas.
- Géneros más vistos.
- Distribución por estado de visualización.

## RF-13 Dashboard Personal

El sistema debe proporcionar un panel principal para cada usuario.

### Información Mostrada

- Anime en progreso.
- Favoritos recientes.
- Estadísticas resumidas.
- Actividad reciente.

## RF-14 Gestión de Roles

El sistema debe manejar roles `USER` y `ADMIN`.

## RF-15 Panel Administrativo

El sistema debe permitir que administradores gestionen la plataforma.

### Funcionalidades

- Consultar usuarios registrados.
- Bloquear usuarios.
- Consultar estadísticas generales del sistema.

## RF-16 Recuperación de Contraseña

El sistema debe permitir solicitar recuperación de contraseña.

### Flujo Esperado

1. El usuario selecciona la opción de recuperación.
2. El usuario ingresa su correo registrado.
3. El sistema genera un token temporal.
4. El sistema envía un correo con enlace de recuperación.
5. El usuario accede al enlace y registra nueva contraseña.
6. El sistema actualiza la contraseña de forma segura.

### Criterios de Aceptación

- El correo debe existir.
- El token debe tener expiración.
- La nueva contraseña debe cumplir reglas de seguridad.
- La contraseña se almacena con hashing.
- El enlace no puede reutilizarse después de cambiar la contraseña.

## RF-17 Inicio de Sesión con Google

El sistema debe permitir registro e inicio de sesión mediante cuenta de Google.

> [!info]
> Esta funcionalidad se clasifica como post-MVP para controlar el alcance inicial.

### Flujo Esperado

1. El usuario selecciona `Continuar con Google`.
2. El sistema redirige al proceso de autenticación de Google.
3. Google valida la identidad.
4. El sistema recibe correo, nombre e imagen de perfil.
5. Si el correo no existe, se crea una cuenta.
6. Si el usuario no tiene username, el sistema solicita uno único.
7. Después de completar el username, el usuario accede a la plataforma.

### Criterios de Aceptación

- El sistema permite iniciar sesión sin contraseña local cuando el proveedor es Google.
- El correo de Google se asocia a la cuenta interna.
- El username sigue siendo único.
- Si el usuario ya existe, inicia sesión normalmente.

## Referencias Relacionadas

- [[Criterios de Aceptación]]
- [[Casos de Uso]]
- [[Reglas de Negocio]]
