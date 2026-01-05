# Operación: backup/restore y actualizaciones

## Backup / restore

- Exporta la configuración a un fichero antes de cambios importantes.
- Guarda backups con fecha (ej.: `backup_2026-01-05.conf`).
- Restaurar sirve para reemplazo de hardware o rollback.

## Actualizaciones

- Mantén el sistema al día usando el mecanismo de actualización integrado.
- Tras actualizar, valida:
  - acceso web
  - interfaces de red
  - un stream de prueba extremo a extremo

## Buenas prácticas

- Convención de nombres para canales y destinos.
- Documenta rangos de puertos y reglas de firewall.
- Cambia una cosa cada vez y valida.
