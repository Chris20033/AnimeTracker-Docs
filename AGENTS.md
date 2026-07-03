# AnimeTracker Agent Instructions

These instructions apply to all work in this workspace.

## Documentation Is Source of Truth

Before making code changes for AnimeTracker, consult the Obsidian documentation starting at:

`AnimeTracker/00 Inicio/AnimeTracker - Índice.md`

Do not add, remove, or change product behavior that contradicts the documentation unless the user explicitly requests a scope change. If the request and documentation conflict, ask one concise clarification question.

## Required Documentation Updates

Every code change must be checked against the documentation. Update docs in the same task when behavior, API, database, architecture, deployment, or scope changes.

Update these areas as needed:

- Requirements: `AnimeTracker/02 Requisitos/`
- Business rules and entities: `AnimeTracker/03 Dominio/`
- Database design: `AnimeTracker/04 Base de Datos/`
- Architecture: `AnimeTracker/05 Arquitectura/`
- Roadmap and MVP scope: `AnimeTracker/06 Roadmap/`
- Diagrams: `AnimeTracker/07 Diagramas/`
- API documentation: `AnimeTracker/08 API/`

## API Work Rules

When implementing or changing an endpoint, update the relevant API note in `AnimeTracker/08 API/` with:

- Method and path.
- Authentication and role requirements.
- Request params, query, and body.
- Success response.
- Error responses.
- Related requirements, use cases, or business rules.

Do not invent endpoint behavior without checking:

- `AnimeTracker/02 Requisitos/Requisitos Funcionales.md`
- `AnimeTracker/03 Dominio/Reglas de Negocio.md`
- `AnimeTracker/05 Arquitectura/Backend.md`
- `AnimeTracker/08 API/API REST.md`

## Scope Rules

The MVP includes registration, login, logout, password recovery, profile management, public profile, anime search/detail, personal library, favorites, basic statistics, and deploy.

Google OAuth, comments, followers, notifications, PWA, advanced admin, and recommendations are post-MVP unless the user explicitly changes the scope.

## Naming Rules

Use these internal library status enum values:

- `WATCHING`
- `COMPLETED`
- `ON_HOLD`
- `DROPPED`
- `PLAN_TO_WATCH`

Do not use inconsistent variants such as `Plan ToWatch`, `Plan to Watch`, or `PlanToWatch` without updating the documentation and schema decision.

## Frontend Quality Rules

When working on frontend screens, components, layouts, Tailwind styles, forms, dashboards, anime cards, profiles, or responsive behavior, use `anime-tracker-frontend-design` and relevant UI skills. The UI should be professional, product-specific, responsive, accessible, and not generic SaaS output.

## Final Response Requirement

When completing a coding task, mention:

- Code changed.
- Documentation changed.
- Tests or verification run.
- Any documentation that still needs review, if applicable.
