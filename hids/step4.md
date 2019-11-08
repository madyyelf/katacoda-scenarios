# Proves de funcionament i alarmes.
Per començar verificarem si el servei de **OSSEC està funcionant** amb `service ossec status`{{execute T1}} i en cas que no ho estigui executarem `service ossec start`{{execute T1}}.

El següent pas serà veure el funcionament del IDS.  **Simularem una indicència**, concretament un intrús que intenta eliminar el rastre esborrant els arxius de *log* del sistema, **i analitzarem com ens avisa OSSEC**. 
## Atac
Per separar una mica el rol d'atacant, netejarem la terminal:

`clear`{{execute T1}}

Per aixecar l'alarma simplement esborrarem l'arxiu */var/log/auth.log* **simulant que un atacant està eliminant els evidències** d'una interussió.  Per fer-ho simplement executarem:

`echo "" > /var/log/auth.log`{{execute T1}}

Un cop feta la malifeta netejem la pantalla per tenir més clar com el IDS ens avisa de la incidència.

`clear`{{execute T1}}
## Alarmes
El que hem fet serà detectat per OSSEC i aixecarà una alarma.  Tanmateix això **pot trigar una mica** ja que OSSEC espaia el monitoratge en el temps per **evitar consumir** molts recursos del sistema i no convertir-se en un inconvenient.
### Logs de OSSEC
Els registres els podem consultar a `/var/ossec/logs/alerts/alerts.log`.  També podeu observar amb un `ls -la /var/ossec/logs/alerts`{{execute T1}} que també existeixen subdirectoris amb **històric** de registres.  Anem a veure quina pinta té l'alerta que hem generat.

`cat /var/ossec/logs/alerts/alerts.log`{{execute T1}}

Veiem quelcom semblant a això:
```
** Alert 1573211133.985: mail - ossex,attack,
2019 Nov 08 11:05:33 host01->ossec-logcollector
Rule: 592 (level 8) -> 'Log file size reduced.'
ossec: File size reduced (inode remained): '/var/log/auth.log'.
```

Amb la qual cosa OSSEC ha **detectat una reducció en el tamany** de l'arxiu *auth.log*, mitjançant la regla 592, classificant-ho com alerta de nivell 8 (una de les més altres) i per tant **l'accó que realitzarà serà enviar un email**.

### Notificació per Email
Si hem configurat correctament el correu electrònic, OSSEC ens enviarà un email d'alerta.  De nou això pot trigar alguns minuts.

Un altre "error" típic és que el gestor de correu classifiqui l'alerta com *spam*, per tant també haurem de **mirar la carpeta de spam*** i fins i tot sería intel·ligent crear regles específiques per aquest tipus de correus.
