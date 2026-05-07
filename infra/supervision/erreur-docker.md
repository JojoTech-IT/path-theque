# 🔑 Gestion des Permissions Volumes
> Résolution des erreurs de type "Permission Denied" dans les containers.

## 🚨 Symptôme : Crash au démarrage
Certains containers (Grafana, Vaultwarden, Postgres) utilisent des utilisateurs non-root pour plus de sécurité. Si le dossier sur l'hôte appartient à `root`, le container crash.

## 🛠️ Solutions par Service

### 📈 Grafana
L'utilisateur interne est `472`.
```bash
sudo chown -R 472:472 ./data/grafana