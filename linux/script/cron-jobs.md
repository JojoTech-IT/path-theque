---
title: cron-jobs
description: 
published: true
date: 2026-04-18T08:04:48.675Z
tags: 
editor: markdown
dateCreated: 2026-04-18T08:04:47.745Z
---

### 4. ⏰ Gestion des tâches Cron
*Chemin : `linux/cron-jobs`*

```markdown
# ⏰ Gestion des tâches Cron
> Automatisation des tâches récurrentes.

## 📝 Syntaxe
`* * * * * commande_a_executer`
`(min) (heure) (jour) (mois) (jour_semaine)`

## 📁 Listes des Crontabs
* **User Jordan** : `crontab -e`
* **Système** : `/etc/crontab`

## 💡 Exemple utile
```bash
# Sauvegarde tous les jours à 03:00
00 03 * * * /opt/scripts/backup_db.sh >> /var/log/cron_backups.log 2>&1