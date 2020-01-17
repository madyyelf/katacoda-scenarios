# Descàrreg
Aquest *Katacoda* s'utilitza a mode de repàs de com s'ha de realitzar una tasca d'aula.  No està pensat com a escenari individual i tampoc està adaptat a *Katacoda*.  Simplement s'utilitza per mostrar les comendes que resolien l'activitat i que l'alumne pugui fer-hi algunes proves més de forma interactiva.

# Enunciat
L’objectiu és crear un tallafocs el màxim segur possible per a una estació de treball Debian Desktop que funciona amb IP fixa dintre del rang que tingueu assignat.  Per assegurar-la al màxim utilitzarem política de llistes blanques tant pel que fa a sortida com d’entrada de comunicacions.

Hem d’acabar aconseguint un tallafocs que faci el següent:
- Establir política de llista blanca (denegar-ho TOT, excepte el que indiquem a continuació).
- Permetre navegar per Internet.
- Permetre actualitzar el sistema (fer un apt-get update i un apt-get upgrade).
- Permetre protocol ICMP (tant rebre’ls com fer-los) per poder utilitzar per exemple el ping.
- Obrir el port 22 TCP d’entrada per a la gestió remota, però tan sols des de la IP i MAC de la vostra màquina real.
Per cada punt cal tenir clara la regla i haver-la comprovat que funciona correctament (que permet i no permet fer el que toca).
