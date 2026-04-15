# 📊 Gestion des Disques & FileSystems
> **Catégorie :** Administration Linux | **Systèmes :** Debian, Ubuntu, Proxmox

---

## 1. Analyse de l'espace global (`df`)
L'outil `df` (Disk Free) permet de visualiser l'occupation des partitions montées.

| Commande | Usage |
| :--- | :--- |
| `df -h` | Affichage lisible (Go, Mo) |
| `df -hT` | Affiche aussi le type de système (ext4, xfs, nfs) |
| `df -i` | **Critique** : Vérifie le nombre d'Inodes restants |

```bash
# Isoler les disques physiques (exclure les systèmes virtuels)
df -hT -x tmpfs -x devtmpfs

2. Structure physique et logique (lsblk)

Avant de manipuler, il faut comprendre comment le stockage est découpé.
Bash

# -f : Affiche les UUID et les formats de fichiers
lsblk -f

Visualisation LVM

Si ton infrastructure utilise LVM (Logical Volume Manager) :

    vgs : Pour voir l'espace libre réel dans ton groupe de disques.

    lvs : Pour voir la taille de chaque volume logique (partition virtuelle).

3. Localiser la consommation (du)

Si une partition frôle les 100%, utilise du (Disk Usage) pour identifier les dossiers coupables.
Scan rapide (Racine)
Bash

du -sh /* 2>/dev/null | sort -h
ou
df -h nom_du_FS

Scan ciblé (ex: logs ou backups)
Bash

# --max-depth=1 évite d'être inondé par les sous-dossiers
du -h --max-depth=1 /var/log | sort -h

4. Dépannage (Quick Fix)
Fichiers supprimés mais encore ouverts

Si df dit que c'est plein mais que du ne trouve rien, un processus retient peut-être un fichier supprimé en mémoire.
Bash

lsof +L1

Action : Redémarrer le service listé (ex: systemctl restart docker).
Erreur "No space left" (Inodes)

Si tu as des Go libres mais que tu ne peux plus écrire, tu n'as plus d'Inodes (trop de petits fichiers).
Vérification : df -i