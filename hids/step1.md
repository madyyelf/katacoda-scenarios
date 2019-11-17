# Preparació del entorn
OSSEC a priori no necessita cap pre-requisit que no instal·li ell mateix.  Tanmateix si volem que ens envii email d'alerta haurem de configurar l'enviament de correu del sistema operatiu tot instal·lant POSTFIX.
## Configuració del sistema per utilitzar Gmail com correu sortint per defecte
***ATENCIÓ***: Aquesta part, si ho feu des de KataCoda, us ho podeu saltar ja que aquest entorn no permetrà les connexions SMTP cap al exterior.  S'hi ha afegit per si voleu fer l'activitat en VM o directament en el vostre Host.
### Instal·lació de paqueteria
Instal·lem mailutils i Postfix junt amb la paqueteria necessària per realitzar les connexions TLS amb Gmail:
`apt install postfix mailutils libsasl2-2 ca-certificates libsasl2-modules`{{execute T1}}
### Configuració de Postfix
Modifiquem o afegim els següents paràmetres de la configuració de Postfix:
`nano /etc/postfix/main.cf`{{execute T1}}

`relayhost = [smtp.gmail.com]:587

smtp_sasl_auth_enable = yes

smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd

smtp_sasl_security_options = noanonymous

smtp_tls_CApath = /etc/ssl/certs

smtpd_tls_CApath = /etc/ssl/certs

smtp_use_tls = yes''{{copy}}

Sortim nano.
### Configuració de les credencials de Gmail
Obrim l'arxiu de configuració del password sasl:
`nano /etc/postfix/sasl_passwd`{{execute T1}}
i dins incloem el servidor SMTP de Gmail junt amb les nostres credencials (tranquils, esteu treballant amb un Docker, per tant en apagar s'esborrarà tot).
`[smtp.gmail.com]:587    USERNAME@gmail.com:PASSWORD`{{copy}}
Un cop fetes les modificacions, sortim de nano i canviem els permissos de l'arxiu per fer-lo segur:
`chmod 400 /etc/postfix/sasl_passwd`{{execute T1}}
L'hi passem a postman les credencials:
`postmap /etc/postfix/sasl_passwd`{{execute T1}}
Finalment reiniciem el servei per a que actualitzi les configuracions:
`/etc/init.d/postfix reload`{{execute T1}}
# Activació google
Cal activar en la nostre compta de Gmail l'"Accés d'aplicacions menys segures", ho trobareu aquí:
https://myaccount.google.com/u/2/lesssecureapps

No cal dir que en acabar la pràctica ho desactiveu!!!
## Proves
Per finalitzar, verifiquem que enviem correctament emails des de terminal:
`echo "Proves enviament email per la activitat de NIDS OSSEC." | mail -s "Proves enviament email IDS" username@gmail.com`{{copy}}
