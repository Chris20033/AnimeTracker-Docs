---
title: Autenticación y Seguridad
tags:
  - animetracker/arquitectura
  - animetracker/seguridad
estado: migrado
fuente:
  - 2_Requisitos.docx
  - 6_Reglas_de_Negocio.docx
  - 7_Arquitectura_del_Sistema.docx
---

# Autenticación y Seguridad

## Autenticación Principal

La autenticación principal se realiza mediante JWT.

Flujo general:

1. El usuario inicia sesión.
2. El backend valida credenciales.
3. El backend genera un token JWT.
4. El frontend almacena temporalmente el token.
5. El token se envía en cada petición protegida.
6. El backend valida el token antes de permitir acceso.

## Registro

Reglas principales:

- Username único.
- Email único.
- Contraseña mínima de ocho caracteres.
- Contraseña almacenada con bcrypt.
- Rol inicial `USER`.
- Usuario activo por defecto.

## Inicio de Sesión con Google

Flujo general:

1. El usuario selecciona `Continuar con Google`.
2. Google valida identidad.
3. El backend recibe datos básicos del usuario.
4. El sistema verifica si el correo ya existe.
5. Si existe, inicia sesión.
6. Si no existe, crea cuenta vinculada a Google.
7. Si falta username, solicita completarlo.

> [!info]
> Google OAuth se recomienda como post-MVP para no bloquear la primera entrega.

## Recuperación de Contraseña

Flujo general:

1. El usuario solicita recuperación.
2. El sistema genera un token temporal.
3. El sistema envía enlace por correo.
4. El usuario registra nueva contraseña.
5. El sistema invalida el token utilizado.

Reglas:

- El token debe expirar.
- El token no debe reutilizarse.
- La nueva contraseña se almacena con hashing.

## Autorización

- Las rutas privadas requieren JWT válido.
- Las rutas administrativas requieren rol `ADMIN`.
- Los usuarios bloqueados no pueden iniciar sesión.

## Medidas de Seguridad

- Contraseñas hasheadas con bcrypt.
- Validación de datos con Zod.
- Rutas protegidas mediante JWT.
- Variables sensibles en `.env`.
- Control de roles.
- Manejo centralizado de errores.
- CORS configurado correctamente.
- No exponer detalles internos en errores públicos.

## Referencias Relacionadas

- [[Flujos de Autenticación]]
- [[Reglas de Negocio]]
- [[Requisitos No Funcionales]]
