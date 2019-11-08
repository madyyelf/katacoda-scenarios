# Proves de funcionament i alarmes.
El següent pas serà veure el funcionament del IDS.  Simularem una indicència, concretament un intrús que intenta eliminar el rastre esborrant els arxius de *log* del sistema, i analitzarem com ens avisa OSSEC. 
## Atac
Per separar una mica el rol d'atacant, netejarem la terminal:

`clear`{{execute T1}}

Per aixecar l'alarma simplement esborrarem l'arxiu */var/log/auth.log* simulant que un atacant està eliminant els evidències d'una interussió.  Per fer-ho simplement executarem:

`echo "" > /var/log/auth.log`{{execute T1}}

Un cop feta la malifeta netejem la pantalla per tenir més clar com el IDS ens avisa de la incidència.

`clear`{{execute T1}}
## Alarmes
ble
### Email
blu
### logs
Els registres els podem consultar a `/var/ossec/logs/alerts/alerts.log`.  També podeu observar amb un `ls -la /var/ossec/logs/alerts`{{execute T1}} que també existeixen subdirectoris amb històric de registres.  Anem a veure quina pinta té l'alerta que hem generat.

`cat /var/ossec/logs/alerts/alerts.log`{{execute T1}}

Veiem quelcom semblant a això:

