# Punt d'instal·lació
Els NIDS necessiten veure el màxim tràfic de xarxa que puguem per detectar el màxim d'anomalies, tanmateix insta·lar-los enmig de la sortida cap a la WAN, com si fos un *proxy*, pot generar problemes greus de rendiment.

La opció més utilitzada i recomanable és realitzar un *PORT MIRRORING* al switch principal de manera que el tràfic surti directe cap a la WAN (i des de la WAN) i alhora sigui enviat cap a un altre port, on hi instal·larem el nostre NIDS que podrà analitzar tranquilament els paquets amb la seguretat que no afectarà el rendiment de la xarxa.

# Instal·lació
Per fer la instal·lació de suricata utilitzarem el repositoris oficials de Ubuntu 19.04 de manera que sempre dispossem d'actualitzacions.

Primer de tot instal·lem els pre-requisits de programari:
- `sudo apt-get install software-properties-common`{{execute T1}}

Després afegim els repositoris de *Suricata* oficials:
- `sudo add-apt-repository ppa:oisf/suricata-stable`{{execute T1}}
- I actualitzem els llistats: `sudo apt-get update`{{execute T1}}

Finalment tan sols cap instal·lar el paquet de *Suricata* pròpiament dit:
- `sudo apt-get install suricata `{{execute T1}}
