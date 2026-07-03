---
title: Arquitectura del Sistema
tags:
  - animetracker/arquitectura
estado: migrado
fuente:
  - 7_Arquitectura_del_Sistema.docx
---

# Arquitectura del Sistema

AnimeTracker utilizará una arquitectura cliente-servidor separando frontend, backend y base de datos.

## Tipo de Arquitectura

La aplicación estará compuesta por tres capas principales:

- Capa de presentación.
- Capa de lógica de negocio.
- Capa de persistencia de datos.

## Capa de Presentación

Corresponde al frontend de la aplicación.

Tecnologías propuestas:

- React.
- Vite.
- React Router.
- TanStack Query.
- Zustand.
- Tailwind CSS.

Responsabilidades:

- Mostrar la interfaz de usuario.
- Gestionar navegación entre páginas.
- Consumir endpoints del backend.
- Administrar estado global del usuario autenticado.
- Mostrar resultados de búsqueda de anime.
- Presentar bibliotecas, perfiles, comentarios y estadísticas.

## Capa de Lógica de Negocio

Corresponde al backend.

Tecnologías propuestas:

- Node.js.
- Express.
- Prisma.
- Zod.
- JWT.
- Bcrypt.

Responsabilidades:

- Gestionar autenticación.
- Validar datos de entrada.
- Procesar reglas de negocio.
- Exponer API REST.
- Comunicarse con base de datos.
- Integrar servicios externos.
- Gestionar autorización mediante roles.

## Capa de Persistencia

Encargada del almacenamiento de información.

Tecnologías propuestas:

- PostgreSQL.
- Prisma ORM.

Responsabilidades:

- Almacenar usuarios.
- Almacenar anime consultado.
- Almacenar bibliotecas personales.
- Almacenar favoritos.
- Almacenar comentarios.
- Almacenar seguidores.
- Almacenar tokens de recuperación.
- Almacenar notificaciones.

## Comunicación Entre Componentes

- El frontend se comunica con backend mediante HTTP y API REST.
- El backend se comunica con PostgreSQL mediante Prisma ORM.
- La integración con APIs externas de anime se realiza desde el backend.

> [!important]
> El frontend no debe consumir directamente la API externa de anime para mantener control sobre normalización, persistencia, caché, reglas y seguridad.

## Estructura General del Proyecto

```text
anime-tracker/
  frontend/
    src/
    public/
    package.json

  backend/
    src/
    prisma/
    package.json

  docker-compose.yml
  README.md
  .gitignore
```

## Justificación Técnica

React, Node.js, Express, PostgreSQL y Prisma permiten construir una aplicación moderna, escalable y cercana a entornos reales de desarrollo Full Stack.

Este stack es adecuado para portafolio profesional porque demuestra habilidades en frontend, backend, diseño de base de datos, autenticación, consumo de APIs externas, despliegue y buenas prácticas de arquitectura.

## Referencias Relacionadas

- [[Diagrama de Arquitectura]]
- [[Backend]]
- [[Frontend]]
- [[Autenticación y Seguridad]]
- [[Despliegue]]
