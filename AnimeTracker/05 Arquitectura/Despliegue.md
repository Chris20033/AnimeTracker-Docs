---
title: Despliegue
tags:
  - animetracker/arquitectura
  - animetracker/deploy
estado: migrado
fuente:
  - 1_Planeacion_AnimeTracker.docx
  - 7_Arquitectura_del_Sistema.docx
  - 8_Roadmap_de_desarrollo.docx
---

# Despliegue

## Plataformas Recomendadas

Frontend:

- Vercel.

Backend:

- Render.
- Railway.

Base de datos:

- PostgreSQL en Render.
- PostgreSQL en Railway.
- Neon.

## Docker Para Desarrollo Local

Docker se utilizará principalmente para desarrollo local.

`docker-compose.yml` debería levantar:

- Backend.
- PostgreSQL.
- Adminer o pgAdmin.

## Variables de Entorno

Variables esperadas:

- `DATABASE_URL`
- `JWT_SECRET`
- `JWT_EXPIRES_IN`
- `FRONTEND_URL`
- `CORS_ORIGIN`
- `KITSU_BASE_URL`
- `GOOGLE_CLIENT_ID`
- `GOOGLE_CLIENT_SECRET`
- `EMAIL_PROVIDER_API_KEY`

> [!warning]
> Los secretos no deben versionarse. Deben definirse en el proveedor de despliegue o en archivos `.env` locales ignorados por Git.

## CI/CD

GitHub Actions debería validar automáticamente:

- Instalación de dependencias.
- Linters.
- Pruebas automatizadas.
- Build del frontend.
- Build del backend.
- Despliegue automático cuando aplique.

## Checklist de Deploy

- Frontend desplegado.
- Backend desplegado.
- Base de datos provisionada.
- Variables de entorno configuradas.
- Migraciones ejecutadas.
- CORS configurado.
- Flujo de autenticación validado.
- Búsqueda de anime validada.
- Biblioteca validada.
- Estadísticas básicas validadas.

## Referencias Relacionadas

- [[Roadmap de Desarrollo]]
- [[Arquitectura del Sistema]]
- [[Requisitos No Funcionales]]
