Erreur :
Failed to start systemd-fsck[…]


1️⃣ Se connecter en root depuis le terminal emergency mode
2️⃣ Identifier le disque fautif avec lsblk -f et blkid
3️⃣ Comparer l'UUID réel avec celui déclaré dans fstab
4️⃣ Réparer le filesystem avec fsck (jamais mkfs, jamais de formatage)
5️⃣ Redémarrer et vérifier le montage
Source :
https://oleks.ca/2026/06/29/restaurer-proxmox-apres-une-erreur-de-disque/
