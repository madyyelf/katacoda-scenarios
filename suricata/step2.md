# Configuració
Ens caldrà fer alguns canvis bàsics a la configuració de *Suricata*.  Aquesta configuració la trobarem a `/etc/suricata/suricata.yaml`.

És bona idea repassar-la ja que trobareu coses com la definició de xarxes i subxarxes, ports, etc necessaries per definir regles *custom*.

## Tarja on escoltar
El que en cal canviar son totes les referències de la tarja `eth0` a `ens3` ja que *Ubuntu 19.04* ja no treballa amb aquesta nomenlatura.

`sed -i 's/eth0/ens3/gI' /etc/suricata/suricata.yaml`{{execute T1}}

# Regles
Les regles en aquesta versió de *Suricata* estàn situades a `/var/lib/suricata/rules`, però el directori no existeix.  Per tant anem a crear-lo:

`mkdir /var/lib/suricata /var/lib/suricata/rules`{{execute T1}}

> **ATENCIÓ:** Actualment aquest directori esta buid, per tant l'hauriem d'omplir amb els arxius de regles que vulguessim controlar.  Alguns els tenim a `/etc/suricat/rules/` i els podem traslladar fent un *copy*.  Si ho fem recordar que tambe cal activar-los editant `/etc/suricata/suricata.yaml` i afegir-los a la secció *rule-files* (cap al final de l'arxiu) tal i com ho farem més endavant amb les regles personalitzades.

> Alguns repositoris de regles per *Suricata*:
> - [emergingthreats.net](https://rules.emergingthreats.net/open/suricata/rules/).
> - [suricata-rules](https://github.com/suricata-rules/suricata-rules).

# Reinici del servei i solució de problema
Un cop configurat *Suricata* re-iniciem el servei per a que agafi els canvis:
- `service suricata restart`{{execute T1}}

Si mirem els *logs* de *Suricata* veurem que tenim un error relacionat amb el *PID* del dimoni:
- `cat /var/log/suricata/suricata.log`{{execute T1}}

Per solucionar-ho farem el que ens diu en el registre de *log*, eliminar el arxiu `suricata.pid`:
- Primer parem el servei: `service suricata stop`{{execute T1}}
- I ara eliminem l'arxiu *PID*: `rm /var/run/suricata.pid`{{execute T1}}

Tornem a iniciar el servei i verifiquem que tot estigui bé:
- `service suricata start`{{execute T1}}
- `service suricata status`{{execute T1}}
- `cat /var/log/suricata/suricata.log`{{execute T1}}

Si tot ha funcionat, tindrem el servei funcionant i els *logs* de *Suricata* sense errors.
