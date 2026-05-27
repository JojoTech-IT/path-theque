---
title: grafana
description: 
published: true
date: 2026-05-07T14:31:52.308Z
tags: 
editor: markdown
dateCreated: 2026-05-07T14:31:51.292Z
---

# 📊 Dashboards Grafana
> Liste des modèles utilisés pour la supervision de l'infrastructure.

## 📥 Procédure d'importation
1. Cliquer sur l'icône **+** (Create) > **Import**.
2. Saisir l'ID du dashboard souhaité.
3. Sélectionner la source de données **Prometheus**.

## 🚀 Top Dashboards (Recommandés)

### 🖥️ 1. Node Exporter Full (ID: 1860)
C'est le dashboard de base pour surveiller la machine hôte.
* **Alertes à surveiller :** Charge CPU > 80%, Utilisation RAM, Remplissage des disques.

### 🐳 2. Docker Containers (ID: 10619)
Permet de voir la consommation individuelle de chaque container.
* **Utilité :** Identifier quel service (ex: `glpi` ou `freshrss`) consomme trop de ressources.

### 🛣️ 3. Traefik (ID: 11462)
Indispensable pour voir le trafic entrant sur ton infra.
* **Métrique clé :** Nombre de codes 4xx (erreurs client) ou 5xx (erreurs serveur).

---
*Note : Pour le dashboard 1860, le container `node-exporter` doit être installé sur la machine.*