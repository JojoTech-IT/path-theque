# 🛠️ Debug Traefik & Containers
> Guide pour résoudre les services "Inaccessibles" malgré un status UP.

## 1. Vérifier les Labels
Traefik a besoin de 3 infos vitales pour router le trafic :
1. **Enable** : `traefik.enable=true`
2. **Host** : La règle `Host(`sub.domain.tld`)`
3. **Port** : `loadbalancer.server.port=XXXX` (Obligatoire si l'image expose plusieurs ports).

## 2. Problème de Réseau
Les containers doivent partager un réseau commun (souvent `proxy-net`).
* Commande pour inspecter le réseau : `docker network inspect proxy-net`
* Vérifier que Traefik **ET** le service cible y figurent.

## 3. Logs utiles
* Voir les erreurs de routing : `docker logs -f traefik`
* Accéder à l'interface Traefik (si activée) : `port 8080`.