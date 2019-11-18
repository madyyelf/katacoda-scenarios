# Personalització de regles.
Tot i que tenim actualitzacions de regles gratuïtes, és interessant crear les nostres pròpies ja que les regles gratuïtes son públiques i per tant els "dolents" també i tenen acces i poden modificar el malware i els atacs per a evadir els patrons de detecció.

És per això que tots els IDS ens permeten crear regles personalitzades, que tan sols coneguem nosaltres, permetent-nos tant evitar que esquivin la detecció com adaptar-nos a nous atacs sense esperar l'alliberament de les regles gratuïtes que els detecten.
## Principis generals
En general respectarem 3 coses:
* No modificar cap arxiu de /var/ossec/rules excepte el local_rules.xml
* Les notres resgles tindràn un ID per sobre de 100000.
* Mantenir ordre en les regles.
## Alerta a apache
Per fer una prova farem una nova regla que monitoritzi els logs de Apache i detecti qui accedeix a certs llocs de la nostra web.
### Entorn
* Per crear l'entorn de proves primer instal·lem Apache: `apt install apache2`{{execute T1}}
* Seguidament creem un arxiu "sensible": `touch /var/www/html/important.html`{{execute T1}}
### Configuració de OSSEC
Ara configurarem OSSEC per a que monitoritzi els logs de Apache2 i reaccioni al detectar que algú accedeix al arxiu important:
* Modificiquem l'arxiu de configuració de OSSEC `nano /var/ossec/etc/ossec.conf`{{execute T1}} i afegir el següent codi dins de la secció < !-- Files to monitor (localfileS) -->:
> <localfile>
  
>  <log_format>syslog</log_format>

>  <location>/var/log/apache2/access.log</location>

> </localfile>

***WORKING ON***

