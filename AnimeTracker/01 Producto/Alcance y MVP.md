---
title: Alcance y MVP
tags:
  - animetracker/producto
  - animetracker/mvp
estado: migrado
fuente:
  - 1_Planeacion_AnimeTracker.docx
  - 2_Requisitos.docx
  - 8_Roadmap_de_desarrollo.docx
---

# Alcance y MVP

El MVP de AnimeTracker debe entregar una versión funcional que permita registrar usuarios, autenticar sesiones, buscar anime, gestionar una biblioteca personal y consultar estadísticas básicas.

## MVP Obligatorio

La primera versión funcional incluirá:

- Registro de usuarios.
- Inicio de sesión.
- Cierre de sesión.
- Autenticación con JWT.
- Recuperación de contraseña.
- Perfil privado y público.
- Búsqueda de anime usando API externa.
- Vista de detalle de anime.
- Agregar anime a biblioteca.
- Cambiar estado de visualización.
- Actualizar episodios vistos.
- Calificar anime.
- Marcar favoritos.
- Estadísticas básicas.
- Deploy funcional.

## Funcionalidades Post-MVP

Estas funcionalidades son valiosas, pero no deberían bloquear el primer release:

- Inicio de sesión con Google.
- Comentarios generales por anime.
- Seguidores.
- Notificaciones.
- Comentarios por episodio.
- Reseñas por episodio.
- Panel administrativo avanzado.
- Aplicación PWA.
- Recomendaciones personalizadas.
- Integración con múltiples APIs.

## Criterio de Cierre del MVP

El MVP puede considerarse completo cuando un usuario pueda:

- Crear una cuenta.
- Iniciar sesión.
- Editar su perfil.
- Buscar anime.
- Ver el detalle de un anime.
- Agregar anime a su biblioteca.
- Actualizar progreso, estado y calificación.
- Marcar favoritos.
- Ver estadísticas básicas.
- Acceder al sistema desplegado desde Internet.

## Decisiones de Alcance

> [!important]
> Para evitar crecimiento excesivo del alcance inicial, las funcionalidades sociales y administrativas avanzadas se documentan como post-MVP.

## Referencias Relacionadas

- [[Requisitos Funcionales]]
- [[MVP]]
- [[Funcionalidades Futuras]]
- [[Roadmap de Desarrollo]]
