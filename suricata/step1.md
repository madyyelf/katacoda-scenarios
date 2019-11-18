# Instal·lació
`sudo apt-get install software-properties-common`{{execute T1}}

`sudo add-apt-repository ppa:oisf/suricata-stable`{{execute T1}}

`sudo apt-get update`{{execute T1}}

`sudo apt-get install suricata `{{execute T1}}
# Reinici del servei i solució de problema
`service suricata stop`{{execute T1}}

`rn /var/run/suricata.pid`{{execute T1}}

`service suricata start`{{execute T1}}

`service suricata status`{{execute T1}}

`cat /var/log/suricata/suricata.log`{{execute T1}}
