---
title: Requisitos No Funcionales
tags:
  - animetracker/requisitos
  - animetracker/no-funcional
estado: creado
fuente:
  - 2_Requisitos.docx
  - 7_Arquitectura_del_Sistema.docx
---

# Requisitos No Funcionales

Este documento consolida requisitos de calidad que estaban implícitos en los documentos originales.

## Seguridad

- Las contraseñas deben almacenarse usando hashing con bcrypt.
- Las rutas privadas deben protegerse con JWT.
- Las variables sensibles deben almacenarse en `.env` y no versionarse.
- El sistema debe validar datos de entrada con Zod.
- CORS debe configurarse explícitamente.
- Las funciones administrativas deben requerir rol `ADMIN`.

## Usabilidad

- La interfaz debe ser moderna y responsiva.
- Los formularios deben mostrar errores claros.
- Las pantallas deben incluir estados de carga, error y vacío.
- El dashboard debe resumir información importante del usuario.

## Mantenibilidad

- El backend debe organizarse por capas: routes, controllers, services, repositories, schemas y middlewares.
- Las reglas de negocio deben centralizarse en services.
- El acceso a datos debe encapsularse con Prisma.
- El código debe usar ESLint y Prettier.

## Escalabilidad

- La arquitectura debe permitir agregar notificaciones, PWA, reseñas, comentarios por episodio y panel administrativo avanzado.
- La información de anime no debe almacenarse masivamente; solo se persisten registros consultados o asociados a usuarios.

## Portabilidad

- Docker Compose debe facilitar el entorno local.
- El proyecto debe poder ejecutarse en otros equipos con una guía de instalación.

## Disponibilidad y Despliegue

- El frontend debe desplegarse en Vercel.
- El backend debe desplegarse en Render o Railway.
- PostgreSQL puede hospedarse en Render, Railway o Neon.
- El sistema debe contar con variables de entorno separadas por ambiente.

## Observabilidad Inicial

- El backend debe manejar errores de forma centralizada.
- Debe existir logging básico de solicitudes o errores relevantes.
- Los errores no deben exponer información sensible al cliente.

## Referencias Relacionadas

- [[Arquitectura del Sistema]]
- [[Autenticación y Seguridad]]
- [[Despliegue]]
