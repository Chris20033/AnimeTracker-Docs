---
title: Integraciones Externas
tags:
  - animetracker/arquitectura
  - animetracker/integraciones
estado: migrado
fuente:
  - 7_Arquitectura_del_Sistema.docx
---

# Integraciones Externas

## API Externa de Anime

La información de anime será obtenida desde una API externa.

Opciones consideradas:

- Jikan API.
- AniList GraphQL API.

## Recomendación Inicial

Para la primera versión se recomienda iniciar con Jikan API por su facilidad de uso.

Posteriormente se puede integrar AniList para practicar GraphQL.

## Estrategia de Consumo

- El backend consume la API externa.
- El frontend consulta únicamente el backend propio.
- El backend normaliza la respuesta externa.
- El backend decide cuándo persistir anime en la base de datos.

## Estrategia de Almacenamiento

El sistema no almacena toda la información disponible de la API externa.

Solo se guardan anime que hayan sido:

- Agregados a una biblioteca.
- Marcados como favoritos.
- Comentados.
- Requeridos por alguna funcionalidad persistente.

Esto evita llenar la base de datos con información innecesaria.

## Google OAuth

Google OAuth permitirá autenticación federada.

Se recomienda implementarlo después del MVP base.

## Servicio de Correo

La recuperación de contraseña requiere un servicio para enviar correos.

Opciones posibles:

- Resend.
- SendGrid.
- Mailgun.
- SMTP tradicional.

## Referencias Relacionadas

- [[Arquitectura del Sistema]]
- [[Autenticación y Seguridad]]
- [[Diseño Lógico]]
