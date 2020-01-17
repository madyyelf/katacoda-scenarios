# Creació de l'estructura
El primer per generar el tallafocs és crear l'estructura de taules i cadenes que permetrà emmagatzemar i treballar amb les regles.

## Creació de taules
Les taules son simples contenidors de cadenes, i per tant s'utilitzen com organitzadors.

Creem la taula `DENEGAR`:
- `nft add table DENEGAR`{{execute T1}}

## Creació de cadenes
Les cadenes, associades a una taula, actuen com a contenidors de regles i alhora van associades a un tipus i punt d'inspecció dels paquets.  També s'associa una prioritat i opcionalment una política per defecte (en aquest cas, al ser llistes negres associem *accept*).

Creem la cadena de `SORTIDA`.
- `nft add chain ip DENEGAR SORTIDA { type filter hook output priority 0 \; policy accept\; }`{{execute T1}}
