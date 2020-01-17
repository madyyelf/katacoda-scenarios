# Creació de regles de filtratge
## Proves prèvies
Primer verifiquem que el ping a `8.8.8.8` funciona correctament:
- `ping 8.8.8.8`{{execute T1}}
## Regla de bloqueig
Per blocar els pings a `8.8.8.8`:
- `nft add rule DENEGA SORTIDA ip protocol icmp ip daddr 8.8.8.8 drop`{{execute T1}}
## Proves de funcionament
Ara farem les proves per verificar que la regla funciona:
- `ping 8.8.8.8`{{execute T1}}

