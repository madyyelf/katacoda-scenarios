# Exploració de l'aplicació.
Ara veurem una mica **com funciona el servei** de OSSEC i **com està organitzat** el programari a nivell de carpetes i arxius de manera que el puguem remenar i **adaptar a les nostres necessitats**.
## Servei
L'aplicació funciona mitjançant **dimoni**, que com tots els serveis de GNU/Linux podem gestionar amb la comanda system.
- **Estat**: Per verificar l'estat del sistema: `system ossec status`{{execute T1}}
- **Iniciar**: Per iniciar el dimoni si estiguès aturat: `system ossec start`{{execute T1}}
- **Parar**: Per parar el dimoni: `system ossec stop`{{execute T1}}
- **Reiniciar**: Per reiniciar el servei i que re-carregui configuracions: `system ossec restart`{{execute T1}}
# Estructura de directoris
Tota la **instal·lació** està a `/var/ossec`
## Directoris importants
- **Binaris**: a `/var/ossec/bin`
- **Registes**: a `/var/ossec/logs`
- **Configuracions**: a `/var/ossec/etc`
## Arxius importants
### Configuració de OSSEC
Si en qualsevol moment volem modificar alguna **configuració**, per exemple el email on enviar les alertes, el servidor SMTP o el conjunt de regles a aplicar ho podrem trobar tot a `/var/ossec/etc/ossec.conf`

