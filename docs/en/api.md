# REST API (Swagger)

OnPremise SRT Server provides a REST API for automation and integration.

## Swagger UI

Access Swagger UI from the device:

- `http://DEVICE_IP/swagger`

## Authentication (high level)

Typical pattern:
1) Call the login endpoint to obtain an `apiKey`.
2) Use the key in subsequent calls:

- Header: `Authorization: apiKey`

## Session timeout

API sessions expire after a period of inactivity. If requests fail due to timeout, renew the session (login again).

## Common use cases

- Create/update inputs and outputs programmatically
- Query status and health
- Integrate with external orchestration tools
