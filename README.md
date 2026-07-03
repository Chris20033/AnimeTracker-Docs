# AnimeTracker Documentation

AnimeTracker is a full stack web application project for tracking anime, managing a personal library, marking favorites, updating episode progress, and viewing basic personal statistics.

This repository contains the product, technical, API, database, roadmap, and architecture documentation for the project. The documentation is organized as an Obsidian vault and acts as the source of truth for implementation decisions.

## Product Vision

AnimeTracker is inspired by platforms like MyAnimeList and AniList, but designed as a professional portfolio project built from scratch.

The goal is to help users answer questions like:

- What anime am I currently watching?
- How many episodes have I watched?
- Which anime have I completed?
- Which anime are pending or dropped?
- What are my favorite genres?
- What does my public anime profile look like?

## MVP Scope

The MVP includes:

- User registration.
- Login and logout.
- Password recovery.
- Private profile management.
- Public user profile.
- Anime search.
- Anime detail page.
- Personal anime library.
- Library status tracking.
- Favorites.
- Basic statistics.
- Deployment.

Post-MVP features include Google OAuth, comments, followers, notifications, PWA support, advanced administration, and personalized recommendations.

## Proposed Tech Stack

### Frontend

- React
- Vite
- React Router
- TanStack Query
- Zustand
- Tailwind CSS

### Backend

- Node.js
- Express
- Prisma
- Zod
- JWT
- Bcrypt

### Database

- PostgreSQL
- Prisma ORM

## Repository Structure

```text
AnimeTracker/
  00 Inicio/          Main index and navigation
  01 Producto/        Product vision, scope, users, modules
  02 Requisitos/      Functional and non-functional requirements
  03 Dominio/         Domain model, entities, business rules
  04 Base de Datos/   Logical design, data dictionary, ER model
  05 Arquitectura/    System, backend, frontend, security, deploy
  06 Roadmap/         MVP, sprint plan, future features
  07 Diagramas/       Mermaid diagrams
  08 API/             REST API documentation
```

## Documentation Entry Point

Start here:

- [`AnimeTracker/00 Inicio/AnimeTracker - Índice.md`](AnimeTracker/00%20Inicio/AnimeTracker%20-%20%C3%8Dndice.md)

Important documents:

- [`Visión del Producto`](AnimeTracker/01%20Producto/Visi%C3%B3n%20del%20Producto.md)
- [`MVP`](AnimeTracker/06%20Roadmap/MVP.md)
- [`Plan de Sprints`](AnimeTracker/06%20Roadmap/Plan%20de%20Sprints.md)
- [`Arquitectura del Sistema`](AnimeTracker/05%20Arquitectura/Arquitectura%20del%20Sistema.md)
- [`API REST`](AnimeTracker/08%20API/API%20REST.md)
- [`Diagrama ER`](AnimeTracker/04%20Base%20de%20Datos/Diagrama%20ER.md)

## Library Status Values

The internal library status enum values are standardized as:

- `WATCHING`
- `COMPLETED`
- `ON_HOLD`
- `DROPPED`
- `PLAN_TO_WATCH`

## Development Rule

Before implementing product behavior, consult the documentation first. Any change to behavior, API contracts, database design, architecture, deployment, or scope should update the corresponding documentation in the same task.

## Current Status

- Documentation migrated from original planning documents.
- Obsidian structure created.
- Product scope and MVP defined.
- API contracts documented.
- Database and architecture documentation drafted.
- Sprint plan created for implementation.
- Frontend quality standards defined for professional, responsive, non-generic UI.
