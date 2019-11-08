# Exploració de l'aplicació.
## Servei
L'aplicació funciona mitjançant **dimoni**, que com tots els serveis de GNU/Linux podem gestionar amb la comanda system.
`system ossec status`{{execute T1}}
`system ossec start`{{execute T1}}
`system ossec stop`{{execute T1}}
`system ossec restart`{{execute T1}}
# Estructura de directoris
Tota la **instal·lació està a /var/ossec**
## Directoris importants
- Binaris: a /var/ossec/bin
- Registes: a /var/ossec/logs
- Configuracions: a /var/ossec/etc
## Arxius importants
### Configuració de OSSEC
Si en qualsevol moment volem modificar alguna **configuració**, per exemple el email on enviar les alertes, el servidor SMTP o el conjunt de regles a aplicar ho podrem trobar tot a `/var/ossec/etc/ossec.conf`

