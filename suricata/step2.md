# Configuració
## Tarja on escoltar
Cal canviar totes les referències de la tarja *eth0* a *ens3*.

`sed -i 's/eth0/ens3/gI' /etc/suricata/suricata.yaml`{{execute T1}}

## Regles
Les regles en aquesta versió de Suricata estàn situades a /var/lib/suricata/rules, però el directori no existeix.  Per tant anem a crear-lo:

`mkdir /var/lib/suricata /var/lib/suricata/rules`{{execute T1}}

**ATENCIÓ:** Actualment aquest directori esta buid, per tant l'hauriem d'omplir amb els arxius de regles que vulguessim controlar.  Alguns els tenim a */etc/suricat/rules/* i els podem traslladar fent un *copy*.  Si ho fem recordar que tambe cal activar-los editant */etc/suricata/suricata.yaml* i afegir-los a la secció *rule-files* (cap al final de l'arxiu).

Alguns repositoris de regles per *Suricata*:
- [emergingthreats.net](https://rules.emergingthreats.net/open/suricata/rules/).
- [suricata-rules](https://github.com/suricata-rules/suricata-rules).
