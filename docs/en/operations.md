# Operations: backup/restore and updates

## Backup / restore

- Export configuration to a file before major changes.
- Keep backups with dates (e.g., `backup_2026-01-05.conf`).
- Restore is useful after hardware replacement or rollback.

## Updates

- Keep the system updated using the built-in update mechanism.
- After updates, validate:
  - web access
  - network interfaces
  - one test stream end-to-end

## Best practices

- Use a consistent naming convention for channels and endpoints.
- Document port ranges and firewall rules in your project notes.
- For long sessions or changes, do one modification at a time and validate.
