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
