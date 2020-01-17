# Creació de regles de filtratge
Ara veurem com fer quelcom semblant però denegant la navegació a `infla.cat`.
## Verificació prèvia
Primer de tot verifiquem que podem navegar a `infla.cat` per fer-ho podem utilitzar la comanda `wget`.
- `wget infla.cat`{{execute T1}} i verifiquem que tenim un arxiu `index.html` de 42Kb aproximadament. I lògicament l'eliminem:
- `rm index.html`{{execute T1}}
## Regla de filtratge
La regla serà la següent:
- `nft add rule DENEGAR SORTIDA ip daddr {10.52.0.101, 213.148.192.9} tcp dport {80, 443} drop`{{execute T1}}
Fixeu-vos que estem cobrint les casuístiques de que es realitzi la connexió des de dins del centre (ip 10.52.0.101) o des de foram alhora que cobrim els protocols 80 (HTTP) i 443 (HTTPS).
## Verificació prèvia
Per acabar verifiquem que la regla funciona i no podem navegar a `infla.cat`.
- `wget infla.cat`{{execute T1}} i verifiquem que no descarrega res i acaba donant un error.
