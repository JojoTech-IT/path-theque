# 🐳 Docker & Docker-Compose
> **Catégorie :** Déploiement | **Statut :** Opérationnel

## 🏗️ Commandes de base
| Action | Commande |
| :--- | :--- |
| Lister les containers | `docker ps -a` |
| Voir les logs en direct | `docker logs -f [name]` |
| Supprimer les ressources inutiles | `docker system prune` |

## 🚀 Docker-Compose (Best Practices)
Pour chaque service, on privilégie l'utilisation d'un fichier `docker-compose.yml`.

```yaml
# Exemple type Pasth Tèque
services:
  app:
    image: vendor/app:latest
    container_name: app-service
    restart: unless-stopped
    networks:
      - pashtèque-network

🧹 Maintenance

Pour mettre à jour une stack sans coupure longue :

    docker compose pull

    docker compose up -d