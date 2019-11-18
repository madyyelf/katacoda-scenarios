# Proves i verificació
Per fer un test sobre *Suricata* i que les regles que hem creat per detectar els *PINGs* funcionen correctament tan sols caldrà fer saltar l'alarma:
- `ping -c 4 8.8.8.8`{{execute T1}}

I verificar que ens apareixen els registres associats a `fast.log` de *suricata*:
- `cat /var/log/suricata/fast.log`{{execute T1}}

Si tot és correcte veurem les alertes en aquest arxiu de *log* que posteriorment podrem recollir amb programari com *Splunk*, *OSSIM* o similar.
