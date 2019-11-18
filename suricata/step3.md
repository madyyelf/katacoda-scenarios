# Personalització
## Crear set de regles personalitzades
- `touch /etc/suricata/rules/local.rules`{{execute T1}}
- `nano /etc/suricata/suricata.yaml`{{execute T1}} i afegir al apartat "rule-files:" `- local.rules`{{copy}}
## Creació de regles
- Editar arxiu de regles `nano /etc/suricata/rules/local.rules`{{execute T1}}.
- Afegir una nova regla `alert icmp any any -> any any (msg: “ICMP detected”; sid:10000001;)`{{copy}}.

