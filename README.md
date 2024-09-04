## Automatische Backups

Der `db_backup` Service erstellt automatisch tägliche Backups der MySQL-Datenbank.

- **Backup-Speicherort**: Die Backups werden im Verzeichnis `./db_backups` auf Ihrem Host-System gespeichert
- **Backup-Frequenz**: 24 Stunden

## Wiederherstellung der Datenbank

Nutzen des `db_restore` Service um die Datenbank aus einem bestimmten Backup wiederherzustellen

```bash
BACKUP_FILE=redmine_backup_2024-09-04_12-00-00.sql docker-compose run db_restore
```
