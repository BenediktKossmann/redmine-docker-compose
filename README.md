## Automatische Backups

Der `db_backup` Service erstellt automatisch tägliche Backups der MySQL-Datenbank.

- **Backup-Speicherort**: Die Backups werden im Verzeichnis `./db_backups` auf Ihrem Host-System gespeichert
- **Backup-Frequenz**: 24 Stunden

## Wiederherstellung der Datenbank

Nutzen des `db_restore` Service um die Datenbank aus einem bestimmten Backup wiederherzustellen

1. Setzen des Dateinamens in der .env Datei

```bash
BACKUP_FILE=redmine_backup_2024-09-04_12-34-13.sql
```

2. Dann führen Sie den folgenden Befehl aus, um die Datenbank wiederherzustellen

```bash
docker-compose run --rm db_restore
```

## Backup manuell ausführen

```bash
docker-compose run --rm db_backup
```

## E-Mail Einstellungen in /config/configuration.yml

```bash
# Email configuration
production:
  delivery_method: :smtp
  smtp_settings:
    address: "smtp.ettinger.local"
    port: 25
    domain: "ettinger.de"
    openssl_verify_mode: 'none'

attachments_storage_path: "/usr/src/redmine/files"
max_attachment_size: 50
gravatar:
  enabled: true
```