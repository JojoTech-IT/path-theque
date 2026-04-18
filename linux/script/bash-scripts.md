# 📜 Scripts d'Automatisation Bash
> Liste des scripts maison pour la gestion de l'infrastructure.

## 📥 Backup de base de données
Lieu : `/opt/scripts/backup_db.sh`
```bash
#!/bin/bash
DATE=$(date +%Y-%m-%d)
BACKUP_DIR="/mnt/backups/sql"
docker exec db_container pg_dump -U user db_name > $BACKUP_DIR/db_$DATE.sql

🛠️ Script d'Update System

Lieu : /opt/scripts/system_update.sh
Bash

#!/bin/bash
apt update && apt upgrade -y && apt autoremove -y