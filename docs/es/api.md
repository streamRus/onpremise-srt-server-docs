# API REST (Swagger)

OnPremise SRT Server dispone de un API REST para automatización e integración.

## Swagger

Acceso a Swagger en el propio equipo:

- `http://IP_DEL_EQUIPO/swagger`

## Autenticación (alto nivel)

Patrón típico:
1) Llamar al endpoint de login para obtener un `apiKey`.
2) Usar esa clave en llamadas posteriores:

- Cabecera: `Authorization: apiKey`

## Caducidad de sesión

Las sesiones del API caducan tras un tiempo sin llamadas. Si fallan peticiones por timeout, renueva la sesión (login de nuevo).

## Casos de uso habituales

- Crear/actualizar inputs y outputs por API
- Consultar estado y salud
- Integrar con herramientas externas de orquestación
