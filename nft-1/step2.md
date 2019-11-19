pas2

Crear la taula `TALLAFOCS`:
- `nft add table TALLAFOCS`{{execute T1}}

Crear cadena de `SORTIDA`.
- `nft add chain ip TALLAFOCS SORTIDA { type filter hokk output priority 0 \; policy accept\; }`{{execute T1}}
