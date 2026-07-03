---
title: Flujos de Autenticación
tags:
  - animetracker/diagramas
  - animetracker/seguridad
estado: creado
fuente:
  - 2_Requisitos.docx
  - 7_Arquitectura_del_Sistema.docx
---

# Flujos de Autenticación

## Login con Email y Contraseña

```mermaid
sequenceDiagram
    actor U as Usuario
    participant F as Frontend
    participant B as Backend
    participant DB as PostgreSQL

    U->>F: Ingresa email y contraseña
    F->>B: POST /api/auth/login
    B->>DB: Busca usuario por email
    DB-->>B: Usuario
    B->>B: Valida bcrypt y estado activo
    B-->>F: JWT + datos de usuario
    F-->>U: Redirige al dashboard
```

## Recuperación de Contraseña

```mermaid
sequenceDiagram
    actor U as Usuario
    participant F as Frontend
    participant B as Backend
    participant DB as PostgreSQL
    participant Mail as Servicio de correo

    U->>F: Solicita recuperar contraseña
    F->>B: POST /api/auth/forgot-password
    B->>DB: Valida email y crea token
    B->>Mail: Envía enlace de recuperación
    Mail-->>U: Correo con enlace
    U->>F: Abre enlace y registra nueva contraseña
    F->>B: POST /api/auth/reset-password
    B->>DB: Valida token, actualiza password_hash y marca token usado
    B-->>F: Confirmación
```

## Login con Google

```mermaid
sequenceDiagram
    actor U as Usuario
    participant F as Frontend
    participant G as Google
    participant B as Backend
    participant DB as PostgreSQL

    U->>F: Selecciona Continuar con Google
    F->>G: Redirección OAuth
    G-->>B: Código o datos OAuth
    B->>G: Valida identidad
    G-->>B: Perfil Google
    B->>DB: Busca usuario por email
    alt Usuario existe
        B->>DB: Vincula cuenta externa si falta
    else Usuario nuevo
        B->>DB: Crea usuario y cuenta externa
    end
    B-->>F: JWT o solicitud de username
    F-->>U: Acceso a plataforma
```

## Referencias Relacionadas

- [[Autenticación y Seguridad]]
- [[Requisitos Funcionales]]
- [[Reglas de Negocio]]
