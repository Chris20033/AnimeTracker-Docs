---
title: Diagrama ER
tags:
  - animetracker/base-de-datos
  - animetracker/diagrama
estado: creado
fuente:
  - 4_Entidades.docx
  - 5_Diseño_logico_base_de_datos.docx
---

# Diagrama ER

```mermaid
erDiagram
    users {
        uuid id PK
        string username UK
        string email UK
        string password_hash
        string avatar_url
        string banner_url
        string bio
        string role
        boolean is_active
        datetime created_at
        datetime updated_at
    }

    external_auth_accounts {
        uuid id PK
        uuid user_id FK
        string provider
        string provider_user_id
        datetime created_at
    }

    password_reset_tokens {
        uuid id PK
        uuid user_id FK
        string token
        datetime expires_at
        datetime used_at
        datetime created_at
    }

    anime {
        uuid id PK
        string external_id
        string title
        string title_english
        text synopsis
        string image_url
        int episodes
        string duration
        string status
        string type
        string season
        int year
        float score
        string source
        datetime created_at
        datetime updated_at
    }

    genres {
        uuid id PK
        string name UK
    }

    anime_genres {
        uuid anime_id FK
        uuid genre_id FK
    }

    user_anime_list {
        uuid id PK
        uuid user_id FK
        uuid anime_id FK
        string status
        int episodes_watched
        int personal_score
        text notes
        date started_at
        date finished_at
        datetime created_at
        datetime updated_at
    }

    favorites {
        uuid id PK
        uuid user_id FK
        uuid anime_id FK
        datetime created_at
    }

    anime_comments {
        uuid id PK
        uuid user_id FK
        uuid anime_id FK
        text content
        boolean is_deleted
        datetime created_at
        datetime updated_at
    }

    follows {
        uuid id PK
        uuid follower_id FK
        uuid following_id FK
        datetime created_at
    }

    notifications {
        uuid id PK
        uuid user_id FK
        string type
        string title
        string message
        boolean is_read
        datetime created_at
    }

    users ||--o{ external_auth_accounts : has
    users ||--o{ password_reset_tokens : requests
    users ||--o{ user_anime_list : owns
    anime ||--o{ user_anime_list : appears_in
    users ||--o{ favorites : marks
    anime ||--o{ favorites : is_marked
    anime ||--o{ anime_genres : has
    genres ||--o{ anime_genres : categorizes
    users ||--o{ anime_comments : writes
    anime ||--o{ anime_comments : receives
    users ||--o{ notifications : receives
    users ||--o{ follows : follower
    users ||--o{ follows : following
```

## Notas de Implementación

- `user_anime_list` representa la biblioteca personal.
- Las funcionalidades de episodios, comentarios por episodio y reseñas pueden añadirse en una fase posterior.
- `favorites` y `user_anime_list` son relaciones separadas para permitir que un anime favorito no necesariamente dependa del estado de biblioteca, aunque se puede exigir existencia previa según regla de negocio.

## Referencias Relacionadas

- [[Diseño Lógico]]
- [[Diccionario de Datos]]
- [[Modelo Conceptual]]
