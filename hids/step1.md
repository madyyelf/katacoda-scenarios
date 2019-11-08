# Descàrrega de l'aplicatiu i preparació.
## Introducció a OSSEC
blabla
## Descàrrega
Descarregar OSSEC, la **versió actual és la 3.4.0** que podeu trobar als [repositoris oficials](https://github.com/ossec/ossec-hids/releases).  Tanmateix aquesta versió **dona problemes d'instal·lació** i per tant utilitzarem la versió més antiga 2.8.3.

Aquesta versió en concret és la d'agent/servidor per GNU/Linux.  Per tant **pot actuar com a servidor** central de tota una xarxa de HIDS o **com a agent** o com a instal·lació **local** que implica agent i servidor en la mateixa màquina i que treballen tan sols en local.

Per descarregar OSSEC tan sols caldrà baixar el seu arxiu comprimit:
`wget https://bintray.com/artifact/download/ossec/ossec-hids/ossec-hids-2.8.3.tar.gz`{{execute T1}}
## Descompressió
Tot seguit descomprimim l'arxiu.
`tar -xvzf ossec-hids-2.8.3.tar.gz`{{execute T1}}
Eliminem el zip per no deixar brossa:
`rm ossec-hids-2.8.3.tar.gz`{{execute T1}}
## Entrar al directori
Un cop descomprimit entrem en el directori i ens preparem per a realitzar la instal·lació.
`cd ossec-hids-2.8.3`{{execute T1}}

