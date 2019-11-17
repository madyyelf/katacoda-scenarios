# Preparació del entorn
## Configuració del sistema per utilitzar Gmail com correu sortint per defecte
`asudo apt-get install postfix mailutils libsasl2-2 ca-certificates libsasl2-modules`{{execute T1}}
`nano /etc/postfix/main.cf`{{execute T1}}

relayhost = [smtp.gmail.com]:587
smtp_sasl_auth_enable = yes
smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd
smtp_sasl_security_options = noanonymous
smtp_tls_CApath = /etc/ssl/certs
smtpd_tls_CApath = /etc/ssl/certs
smtp_use_tls = yes

Sortim nano.

`echo "[smtp.gmail.com]:587    USERNAME@gmail.com:PASSWORD" > /etc/postfix/sasl_passwd`{{copy}}
`sudo chmod 400 /etc/postfix/sasl_passwd`{{execute T1}}
`sudo postmap /etc/postfix/sasl_passwd`{{execute T1}}
`sudo /etc/init.d/postfix reload`{{execute T1}}

## Proves
`echo "Proves enviament email per la activitat de NIDS OSSEC." | mail -s "Proves enviament email IDS" username@gmail.com`{{copy}}
