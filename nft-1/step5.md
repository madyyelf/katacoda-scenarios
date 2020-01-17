# Llistat de regles
Per veure l'estructura que hem creat podem realitzar les següents comandes:
- Llistar les taules amb `nft list tables`{{execute T1}}
- Llistar les cadenes i regles de la taula `DENEGAR`: `nft list table DENEGAR`{{execute T1}}
- Llistar tot el tallafocs amb `nft list ruleset`{{execute T1}}

# Persistència
Per aconseguir que aquest tallafocs fos persistent (no s'eliminés en reiniciar) caldría fer:
- Backup del tallafocs anterior: `cp /etc/nftables.conf /etc/nftables.conf.backup`{{execute T1}}
- Guardat del tallafocs actual: `nft list ruleset > /etc/nftables.conf`{{execute T1}}

# Eliminació de regles
Per eliminar una regla necessitem el seu *handle*.  Per veure-ho podem llistar utilitzant l'opció *-a*
- `nft list ruleset -a`{{execute T1}}
Si, per exemple, la regla que volem eliminar té en *handle 2* farem:
- `nft delete rule DENEGAR SORTIDA handle 2`{{execute T1}}
