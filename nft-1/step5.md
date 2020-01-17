# Llistat de regles
Per veure l'estructura que hem creat podem realitzar les següents comandes:
- Llistar les taules amb `nft list tables`{{execute T1}}
- Llistar les cadenes i regles de la taula `DENEGAR`: `nft list table DENEGAR`{{execute T1}}
# Persistència
Per aconseguir que aquest tallafocs fos persistent (no s'eliminés en reiniciar) caldría fer:
- Backup del tallafocs anterior: `cp /etc/nftables.conf /etc/nftables.conf.backup`{{execute T1}}
- Guardat del tallafocs actual: `nft list ruleset > /etc/nftables.conf`{{execute T1}}
