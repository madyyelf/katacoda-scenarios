# Creació de regles de filtratge

Blocar els pings a `8.8.8.8`:
- `nft add rule TALLAFOCS SORTIDA ip protocol icmp ip daddr 8.8.8.8 drop`{{execute T1}}

Proves:
- `ping 8.8.4.4`{{execute T1}}
- `ping 8.8.8.8`{{execute T1}}
