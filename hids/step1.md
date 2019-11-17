# Preparació del entorn
## Configuració del sistema per utilitzar Gmail com correu sortint per defecte
`apt install -y ssmtp mailutils postfix`{{execute T1}}
`nano /etc/ssmtp/ssmtp.conf`{{execute T1}}

AuthUser=youruser@gmail.com
AuthPass=your_strong_password
FromLineOverride=YES
mailhub=smtp.gmail.com:587
UseSTARTTLS=YES

Sortim nano.

Test del servidor d'email:
`echo "This is a test" | mail -s "Test" myuser@gmail.com`{{execute T1}}
