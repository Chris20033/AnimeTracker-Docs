---
title: Backend
tags:
  - animetracker/arquitectura
  - animetracker/backend
estado: migrado
fuente:
  - 7_Arquitectura_del_Sistema.docx
---

# Backend

El backend contiene la lógica de negocio, validaciones, seguridad, acceso a datos e integración con servicios externos.

## Tecnologías

- Node.js.
- Express.
- Prisma.
- PostgreSQL.
- Zod.
- JWT.
- Bcrypt.

## Estructura Propuesta

```text
backend/
  src/
    config/
    controllers/
    services/
    repositories/
    routes/
    middlewares/
    schemas/
    utils/
    server.js

  prisma/
    schema.prisma

  package.json
```

## Controllers

Responsables de recibir peticiones HTTP y devolver respuestas al cliente.

Responsabilidades:

- Recibir parámetros.
- Llamar servicios.
- Manejar respuestas.
- Enviar códigos HTTP adecuados.

## Services

Contienen la lógica de negocio.

Responsabilidades:

- Validar reglas de negocio.
- Coordinar operaciones complejas.
- Procesar datos antes de enviarlos a base de datos.
- Integrar servicios externos cuando sea necesario.

## Repositories

Responsables del acceso a datos.

Responsabilidades:

- Consultar base de datos.
- Crear registros.
- Actualizar registros.
- Eliminar registros.
- Encapsular consultas realizadas con Prisma.

## Routes

Definen endpoints disponibles de la API.

Rutas propuestas:

- `/api/auth`
- `/api/users`
- `/api/anime`
- `/api/library`
- `/api/favorites`
- `/api/comments`
- `/api/follows`
- `/api/notifications`

## Middlewares

Procesan solicitudes antes de llegar a controllers.

Casos principales:

- Verificar autenticación.
- Validar roles.
- Manejar errores.
- Validar tokens.
- Registrar solicitudes.

## Schemas

Definen validaciones de entrada con Zod.

Ejemplos:

- Registro.
- Login.
- Actualización de perfil.
- Comentarios.
- Biblioteca.

## Principios de Implementación

- Controllers no deben contener lógica de negocio compleja.
- Services aplican reglas de negocio.
- Repositories encapsulan Prisma.
- Schemas validan entrada antes de ejecutar lógica.
- Middlewares centralizan autenticación, autorización y errores.

## Referencias Relacionadas

- [[Arquitectura del Sistema]]
- [[Autenticación y Seguridad]]
- [[Integraciones Externas]]
- [[Diseño Lógico]]
