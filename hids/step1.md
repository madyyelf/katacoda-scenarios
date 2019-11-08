# Descàrrega de l'aplicatiu i preparació.
## Introducció a OSSEC
blabla
## Descàrrega
Descarregar OSSEC, en aquest cas la versió 3.4.0, dels [repositoris oficials](https://github.com/ossec/ossec-hids/releases).

Aquesta versió en concret és la d'agent/servidor per GNU/Linux.  Per tant pot actuar com a servidor central de tota una xarxa de HIDS o com a agent (ja sigui solitari o integrat amb un altre equip que faci de servidor).

`wget https://bintray.com/artifact/download/ossec/ossec-hids/ossec-hids-2.8.3.tar.g`{{execute T1}}
## Descompressió
`tar -xvzf 3.4.0.tar.gz`{{execute T1}}
## Entrar al directori
`cd ossec-hids-2.8.3`{{execute T1}}

