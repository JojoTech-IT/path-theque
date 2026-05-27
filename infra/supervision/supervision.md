---
title: supervision
description: 
published: true
date: 2026-05-07T14:31:53.824Z
tags: 
editor: markdown
dateCreated: 2026-05-07T14:31:52.795Z
---

# 📈 Monitoring (Grafana & Prometheus)
> **Statut :** Supervision de l'infrastructure Pasth Tèque.

## 🔗 Accès aux services
| Service | URL | Rôle |
| :--- | :--- | :--- |
| **Grafana** | `https://monitor.votre-domaine.fr` | Visualisation (Dashboards) |
| **Prometheus** | Interne (`port 9090`) | Collecte des métriques |

## 🛠️ Configuration Traefik
Pour que Grafana soit exposé, les labels suivants sont indispensables :
1. `traefik.enable=true`
2. `Host(monitor.domaine.fr)`
3. `loadbalancer.server.port=3000`

## 📊 Dashboards à importer
* **Node Exporter Full** (ID: 1860) : Pour la santé des serveurs Linux.
* **Docker Monitoring** (ID: 10619) : Pour l'état des containers.