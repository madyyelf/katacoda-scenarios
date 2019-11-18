# Instal·lació
Per fer la instal·lació de suricata utilitzarem el repositoris oficials de Ubuntu 19.04 de manera que sempre dispossem d'actualitzacions.

Primer de tot instal·lem els pre-requisits de programari:
- `sudo apt-get install software-properties-common`{{execute T1}}

Després afegim els repositoris de *Suricata* oficials:
- `sudo add-apt-repository ppa:oisf/suricata-stable`{{execute T1}}
- I actualitzem els llistats: `sudo apt-get update`{{execute T1}}

Finalment tan sols cap instal·lar el paquet de *Suricata* pròpiament dit:
- `sudo apt-get install suricata `{{execute T1}}
