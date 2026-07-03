---
name: anime-tracker-docs
description: Use when working on AnimeTracker code, API endpoints, database models, features, architecture, documentation, or implementation decisions. Requires consulting and updating the Obsidian documentation before and after code changes.
---

# AnimeTracker Documentation Guardrail

Use this skill whenever the task touches AnimeTracker code, API design, database schema, business rules, frontend behavior, backend behavior, architecture, deployment, roadmap, or documentation.

The documentation in `AnimeTracker/` is the source of truth for product behavior and technical scope. Do not add, remove, or change behavior that contradicts it unless the user explicitly asks to change the documentation and implementation together.

## Required Workflow

Before changing code:

1. Read `AnimeTracker/00 Inicio/AnimeTracker - Índice.md`.
2. Identify which documentation areas are relevant to the task.
3. Read the relevant notes before deciding the implementation.
4. If documentation conflicts with the request, stop and ask one concise clarification question.
5. If documentation is missing, add or update the appropriate note before or alongside implementation.

After changing code:

1. Update all affected documentation.
2. Update API docs when endpoints, request payloads, response payloads, status codes, auth rules, or errors change.
3. Update database docs when models, tables, fields, enums, indexes, constraints, or relationships change.
4. Update requirements or business rules when behavior changes.
5. Update diagrams when architecture, flows, or database relationships change.
6. Mention documentation updates in the final response.

## Documentation Map

Start here:

- `AnimeTracker/00 Inicio/AnimeTracker - Índice.md`
- `AnimeTracker/00 Inicio/Decisiones y Supuestos.md`
- `AnimeTracker/00 Inicio/Glosario.md`

Product and scope:

- `AnimeTracker/01 Producto/Visión del Producto.md`
- `AnimeTracker/01 Producto/Alcance y MVP.md`
- `AnimeTracker/01 Producto/Usuarios y Roles.md`
- `AnimeTracker/01 Producto/Módulos Principales.md`

Requirements:

- `AnimeTracker/02 Requisitos/Requisitos Funcionales.md`
- `AnimeTracker/02 Requisitos/Requisitos No Funcionales.md`
- `AnimeTracker/02 Requisitos/Criterios de Aceptación.md`
- `AnimeTracker/02 Requisitos/Casos de Uso.md`

Domain and business rules:

- `AnimeTracker/03 Dominio/Modelo Conceptual.md`
- `AnimeTracker/03 Dominio/Entidades.md`
- `AnimeTracker/03 Dominio/Reglas de Negocio.md`

Database:

- `AnimeTracker/04 Base de Datos/Diseño Lógico.md`
- `AnimeTracker/04 Base de Datos/Diccionario de Datos.md`
- `AnimeTracker/04 Base de Datos/Diagrama ER.md`

Architecture:

- `AnimeTracker/05 Arquitectura/Arquitectura del Sistema.md`
- `AnimeTracker/05 Arquitectura/Backend.md`
- `AnimeTracker/05 Arquitectura/Frontend.md`
- `AnimeTracker/05 Arquitectura/Autenticación y Seguridad.md`
- `AnimeTracker/05 Arquitectura/Integraciones Externas.md`
- `AnimeTracker/05 Arquitectura/Despliegue.md`

Roadmap:

- `AnimeTracker/06 Roadmap/Roadmap de Desarrollo.md`
- `AnimeTracker/06 Roadmap/MVP.md`
- `AnimeTracker/06 Roadmap/Funcionalidades Futuras.md`

API:

- `AnimeTracker/08 API/API REST.md`
- `AnimeTracker/08 API/Convenciones de Respuesta.md`
- `AnimeTracker/08 API/Errores y Códigos HTTP.md`
- Endpoint-specific notes in `AnimeTracker/08 API/`.

## API Design Rules

When defining or implementing an endpoint, document:

- HTTP method and path.
- Authentication requirement.
- Required role, if any.
- Request params, query, and body.
- Success response shape.
- Error responses and status codes.
- Business rules applied.
- Related requirement IDs or use cases.

Prefer REST endpoints under `/api`:

- `/api/auth`
- `/api/users`
- `/api/anime`
- `/api/library`
- `/api/favorites`
- `/api/statistics`
- `/api/admin`

Do not introduce a new endpoint group without documenting why.

## Current Product Constraints

MVP includes:

- Registration.
- Login and logout.
- Password recovery.
- Profile management.
- Public profile.
- Anime search and detail.
- Personal library.
- Favorites.
- Basic statistics.
- Deployment.

Post-MVP unless the user explicitly changes scope:

- Google OAuth.
- General comments.
- Followers.
- Notifications.
- Episode comments.
- Episode reviews.
- PWA.
- Advanced admin panel.
- Personalized recommendations.

## Naming Decisions

Use these internal enum values for library status:

- `WATCHING`
- `COMPLETED`
- `ON_HOLD`
- `DROPPED`
- `PLAN_TO_WATCH`

UI labels may be localized as:

- Viendo.
- Completado.
- En pausa.
- Abandonado.
- Planeado.

## Database Documentation Rules

When database-related code changes:

- Update `Diseño Lógico.md` for table/model structure.
- Update `Diccionario de Datos.md` for field definitions and constraints.
- Update `Diagrama ER.md` for relationship changes.
- Update `Reglas de Negocio.md` if constraints affect behavior.

## Documentation Update Checklist

Use this checklist at the end of code tasks:

- Did the implementation match documented scope?
- Did any endpoint docs need updates?
- Did any requirements or acceptance criteria change?
- Did any business rules change?
- Did any database docs or diagrams change?
- Did roadmap or MVP scope change?

If the answer is yes to any item, update the corresponding note before finishing.
