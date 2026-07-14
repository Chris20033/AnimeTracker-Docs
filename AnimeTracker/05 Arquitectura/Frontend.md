---
title: Frontend
tags:
  - animetracker/arquitectura
  - animetracker/frontend
estado: migrado
fuente:
  - 7_Arquitectura_del_Sistema.docx
---

# Frontend

El frontend corresponde a la capa de presentación de AnimeTracker.

## Tecnologías

- React.
- Vite.
- React Router.
- TanStack Query.
- Zustand.
- Tailwind CSS.

## Responsabilidades

- Mostrar la interfaz de usuario.
- Gestionar navegación entre páginas.
- Consumir endpoints del backend.
- Administrar estado global de autenticación.
- Mostrar resultados de búsqueda de anime.
- Presentar biblioteca, perfiles, comentarios y estadísticas.

## Páginas Sugeridas

- Landing o página inicial.
- Registro.
- Login.
- Recuperación de contraseña.
- Dashboard.
- Perfil privado.
- Perfil público.
- Búsqueda de anime.
- Detalle de anime.
- Biblioteca personal.
- Favoritos.
- Estadísticas.
- Panel administrativo.

## Estado Cliente

Zustand puede encargarse de estado global mínimo:

- Usuario autenticado.
- Token o estado de sesión.
- Preferencias de interfaz.

TanStack Query debería encargarse de estado servidor:

- Datos de anime.
- Perfil.
- Biblioteca.
- Favoritos.
- Estadísticas.

## Experiencia de Usuario

La interfaz debe incluir:

- Diseño responsivo.
- Skeleton loaders.
- Estados de carga.
- Estados vacíos.
- Manejo de errores.
- Accesibilidad básica.

## Patrones de Estado y Accesibilidad

El frontend usa patrones visuales compartidos en `src/styles/globals.css` para mantener la experiencia consistente:

- `.screen-state` para estados vacíos, errores de pantalla y rutas no encontradas con jerarquía visual clara.
- `.skeleton-shimmer` para loaders de contenido en páginas, paneles y listas.
- `.state-error` y `.state-success` para feedback explícito en formularios y mutaciones.
- Foco global con `:focus-visible` para links, botones, inputs, selects, textareas y summaries.
- `prefers-reduced-motion: reduce` desactiva animaciones/transiciones largas y mantiene el scroll sin movimiento.

Las páginas modificadas deben conservar labels visibles, nombres accesibles para botones de ícono, estados `role="alert"` cuando aplique y responsive funcional desde 320px.

## Estrategia de Pruebas Frontend

El frontend usa Vitest, React Testing Library, Jest DOM y jsdom para validar comportamiento de UI sin depender del backend real.

- `npm run test` ejecuta la suite frontend con `vitest run`.
- `src/test/setup.ts` registra matchers de `@testing-library/jest-dom`.
- `src/test/test-utils.tsx` centraliza providers de prueba con `QueryClientProvider` y `MemoryRouter`.
- Las pruebas priorizan validaciones, formularios, estados de carga/error/empty y componentes principales de estadísticas/favoritos.
- Las llamadas reales a API no se ejercitan en esta suite mínima; cuando un componente depende de estado remoto inevitable, se usa mock del hook correspondiente.

La cobertura mínima del Sprint 10 frontend incluye:

- Validaciones de login, registro, recuperación y reset de contraseña.
- Componentes de formulario (`TextField`, `SubmitButton`) y formularios auth principales.
- Componentes de estadísticas (`StatisticsCards`, `StatusDistributionPanel`, `TopGenresPanel`).
- Panel de favoritos y estados de anime/rutas.

## Carga de Rutas

El router del frontend debe priorizar una carga inicial ligera:

- La landing principal (`HomePage`), layouts, navegación y providers se cargan de forma directa.
- Las páginas secundarias se cargan bajo demanda con `React.lazy` y `Suspense` desde `src/app/router/AppRouter.tsx`.
- Las rutas de autenticación, catálogo, detalle de anime, biblioteca, perfiles, dashboard y `NotFound` no deben importarse estáticamente en el router si no son necesarias para la primera visita.
- El fallback de ruta debe ser visible, accesible con `aria-live`/`aria-busy` y funcionar en light/dark mode usando tokens CSS existentes.
- Este patrón reduce el JavaScript inicial en producción y evita que una visita al homepage cargue código de pantallas no utilizadas.

## Estándar Visual

AnimeTracker debe evitar interfaces genéricas. Las pantallas deben sentirse como un producto de seguimiento de anime y biblioteca personal, con una dirección visual intencional, jerarquía clara, navegación cuidada y estados de interfaz completos.

Para tareas de UI se deben usar las skills frontend instaladas cuando apliquen:

- `anime-tracker-frontend-design` para dirección visual del proyecto.
- `ui-skills-root` para enrutar tareas UI generales.
- `baseline-ui` para pulido de spacing, jerarquía y tipografía.
- `fixing-accessibility` para accesibilidad.
- `fixing-motion-performance` para animaciones y transiciones.
- `taste-skill` o `redesign-skill` para evitar resultados genéricos.

## Referencias Relacionadas

- [[Arquitectura del Sistema]]
- [[Requisitos No Funcionales]]
- [[Módulos Principales]]
- [[Plan de Sprints]]
