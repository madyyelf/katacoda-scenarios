# Personalització
## Crear set de regles personalitzades
- `touch /var/lib/suricata/rules/local.rules`{{execute T1}}
- `nano /etc/suricata/suricata.yaml`{{execute T1}} i afegir al apartat "rule-files:" `- local.rules`{{copy}}
## Creació de regles
- Editar arxiu de regles `nano /var/lib/suricata/rules/local.rules`{{execute T1}}.
- Afegir una nova regla `alert icmp any any -> any any (msg:"ICMP detected"; sid:1; rev:1; classtype:icmp-custom-event;)`{{copy}}.

Tb classificador:
- `nano /etc/suricata/classification.config`{{execute T1}}
- `config classification: icmp-custom-event, ICMP event,2`{{copy}}

## Reiniciar el servei per aplicar canvis
- `service suricata restart`{{execute T1}}
- `cat /var/log/suricata/suricata.log`{{execute T1}}

