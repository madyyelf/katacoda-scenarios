# Creació de l'estructura

## Creació de taules

Crear la taula `TALLAFOCS`:
- `nft add table TALLAFOCS`{{execute T1}}

## Creació de cadenes

Crear cadena de `SORTIDA`.
- `nft add chain ip TALLAFOCS SORTIDA { type filter hook output priority 0 \; policy accept\; }`{{execute T1}}
