Un cop dins del directori de OSSEC tan sols ens caldrà **llançar l'instal·lador** i **seguir l'assistent**, tot triant les **opcions** que ens interessin.
# Instal·lació
Per llançar l'instal·lador tan sols cal executar `./install.sh`{{execute T1}}
# Configuració
Un cop dins l'assitent del instal·lador hem d'anar especificant els paràmetres de la nostra instal·lació.  Anem pas a pas
- Ens demana el idioma que volem utiltizar, en el nostre cas `es`{{execute T1}}
- Ens apareix un //baner// alertant que iniciem la instal·lació per tant hem de fer `s`{{execute T1}}.
1.- El següent pas ès molt important, hem de triar el **tipus de instal·lació** per la pràctica triarem `local`{{execute T1}} per a fer una instal·lació en un únic equip, però si desplemen una instal·lació en xarxa caldria emprar servidor o agente.
2.- Ara ens demana on volem instal·lar OSSEC.  L'opció per defecte de `/var/ossec`{{execute T1}} ja ens serveix.
3.1- Ens demana si volem rebre alertes per correu electrònic, aquesta és una manera ideal per estar al cas de les incidències, per tant diem que si: `s`{{execute T1}}.  I tot seguit hem d'escriure el nostre email on volem rebre les notificacions, i després el servidor smtp a utilitzar per enviar el correu (el `alt3.gmail-smtp-in.l.google.com`{{execute T1}} ja farà el fet).
3.2.- Quan ens demana sobre el "servidor de integridad del sistema" es refereix a verificar que els canvis en el sistema siguin controlats (per exemple, que els arxius log del sistema no perdin tamany).  Somen que si: `s`{{execute T1}}
3.3.- Sistema de tetecció de **rootkits**, de nou si `s`{{execute T1}} ja que així detectara programari de gestió remota com *backdoors*, etc.
3.4.- L'opció de *respostes actives* és molt interessant ja que permetrà programar scripts que es llançaràn automàticament en detectar certs events.  Això ens permet convertir el nostre *IDS* en *IPS*! Per tant donarem de nou a si `s`{{execute T1}}.

Al triar *si* en l'opció anterior ara ens demanarà si volem *descartar paquets* al tallafocs.  Això permetrà que si es detecta un atac per xarxa (per exemple un atac de força bruta al servei SSH) automàticament es crei una regla per bloquejar la IP atacant.  Com veieu és super interessant per tant tornem a donar que si `s`{{execute T1}}.

De nou, això desencadena una nova opció, en aquest cas crear un llistat de *IP blanques* que mai seràn bloquejades.  En principi no ens caldrà cap extra `n`{{execute T1}}, però en un entorn empresarial podria ser interessant afegir la del administrador de sistemes.

Amb això acabem l'assistent, ens apareix un missatge final que podem passar `s`{{execute T1}} i veurem com el instal·lar procedeix a intal·lar OSSEC.

Un últim missatge informa que tot s'ha instal·lat correctament `s`{{execute T1}}.

# Eliminar carpeta de instal·lació
Per deixar el sistema net, eliminarem la carpeta de insta·lació:
`cd ..`{{execute T1}}
`rm -R ossec-hids-2.8.3`{{execute T1}}
