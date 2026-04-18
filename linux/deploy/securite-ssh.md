## 2. 🛡️ Sécurisation SSH (Hardening)
*Chemin : `linux/ssh-hardening`*

```markdown
# 🛡️ Sécurisation SSH (Hardening)
> **Objectif :** Réduire la surface d'attaque du serveur.

## 📝 Configuration recommandée
Éditer le fichier `/etc/ssh/sshd_config` :

* **Changer le port par défaut** : `Port 2222` (optionnel mais réduit le spam)
* **Désactiver le root login** : `PermitRootLogin no`
* **Forcer les clés SSH** : `PasswordAuthentication no`
* **Limiter les utilisateurs** : `AllowUsers jordan`

## 🔐 Gestion des clés
Générer une clé robuste :
```bash
ssh-keygen -t ed25519 -C "jordan@pashtèque"