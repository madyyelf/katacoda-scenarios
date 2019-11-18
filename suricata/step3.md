# Personalització
Ara crearem una relga personalitzada que ens detecti per exemple un *PING* i ens alerti.  Aquest exemple sencill ens servirà coma base per explorar noves funcionalitats i crear les nostres pròpies regles de *Suricata*.

Crear regles personalitzades és interessant per dos motius:
- Els "dolents" no les conneixen (no son públiques) i per tant no poden adaptar els seus atacs per evitar el nostre *NIDS*.
- Podem crear regles per atacs *0 Day* i estar protegits molt abans de que surtin relges oficials per aquests atacs.

# Crear set de regles personalitzades
Les nostres regles les crearem en un arxiu anomenat `local.rules`, tot i que es podria dir de qualsevol manera:
- `touch /var/lib/suricata/rules/local.rules`{{execute T1}}

També haurem d'inscriure a *Suricata* el nostre arxiu de regles per aque el llegeixi i l'incorpori:
- `nano /etc/suricata/suricata.yaml`{{execute T1}} i afegir al apartat "rule-files:" (està cap al final) `- local.rules`{{copy}}.

Amb aquests dos passos hem creat el nostre set de regles `local.rules`, encara buit, i hem indicat a *Suricata* que l'utilitzi.

# Creació de regles
Ara definiriem la regla que utilitzarem per detectar els paquests *ICMP* del *PING*.  Per fer-ho l'afegirem dins de les nostres `local.rules`:

- Editar arxiu de regles `nano /var/lib/suricata/rules/local.rules`{{execute T1}}.
- Afegir una nova regla `alert icmp any any -> any any (msg:"ICMP detected"; sid:1; rev:1; classtype:icmp-custom-event;)`{{copy}}.

Si analitzem la regla veurem que la sintàxis és simple:
- `alert`: És una paraula clau per l'acció d'aixecar l'alerta.
- `icmap`: Protocol.
- `any`: Origen (IP).
- `any`: Port.
- `->`: Comunicació unidireccional, n'hi han varis tipus.
- `any`: Destí (IP).
- `any`: Port.
- `msg`: Missatge per al logs.
- `sid`: Identificador de la regla.
- `rev`: Revisió de la regla.
- `classtype`: Classificació per families de la regla.

# Creació del classificador
També ens caldrà crear el classificador, o familia d'alertes o tag, ja que ara per ara no en tenim cap propi:
- Obrim l'arxiu que conté la configuració dels classificadors: `nano /etc/suricata/classification.config`{{execute T1}}
- I **al final de tot** hi afegim una secció nova amb el nostre classificador: `config classification: icmp-custom-event, ICMP event,2`{{copy}}.

# Reiniciar el servei per aplicar canvis
Un cop tot creat i configurat, tan sols ens caldrà reiniciar el servei per aplicar els canvis:
- `service suricata restart`{{execute T1}}
- I verifiquem als *logs* que no hi ha cap error: `cat /var/log/suricata/suricata.log`{{execute T1}}

