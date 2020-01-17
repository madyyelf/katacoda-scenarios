# Instal·lació de NFtables
Com sempre, instal·lem *NFtables*:
- `apt install nftables`{{execute T1}}

# Estructura per les regles
Per poder afegir regles al nostre tallafocs cal crear una estructura de contenidors format per *taules* i *cadenes* que les contnguin.

Recordeu que les *taules* son simples contenidors per organitzar el tallafocs, i les *cadenes* seràn contenidors de regles i estaràn lligades a un dels punts d'inspecció que implementa el *kernel de linux* i que son els que recorren els paquets.

En aquest escenari filtrarem el protocol *IPv4*, tant d'entrada com de sortida a la màquina amb llistes blanques.  Per tant la nostra estructura podria ser:
- `nft add table DENEGAR`{{execute T1}} per crear una taula de regles per denegar paquets / connexions.
- `nft add chain ip DENEGAR ENTRADA {type filter hook input priority 0\; policy drop\;}`{{execute T1}} per crear una cadena anomenada *ENTRADA* i associada amb el filtratge de paquets d'entrada.  A més, afegim que la política per defecte sigui *drop*, és a dir, treballarem amb llistes blanques.
- `nft add chain ip DENEGAR SORTIDA {type filter hook output priority 0\; policy drop\;}`{{execute T1}} per crear una cadena anomenada *SORTIDA* i associada amb el filtratge de paquets de sortida.  A més, afegim que la política per defecte sigui *drop*, és a dir, treballarem amb llistes blanques.
