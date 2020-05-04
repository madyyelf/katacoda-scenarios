# Preparar el sistema
Primer de tot actualitzarem la màquina i els seus repostirois:
- `apt update && apt upgrade -y`{{execute T1}}
# Instal·lar pre-requisits
Un cop tenim el sistema en l'última versió instal·larem la paqueteria que conforma els pre-requisits de Docker.
- `apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common`{{execute T1}}
# Afegir repositoris de Docker
 Descarreguem i afegim al anell de claus les claus GPG dels repositoris de Docker, per poder autenticar el servidor i fer una descàrrega encriptada:
 - `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`{{execute T1}}
 Afegir els repositoris de Docker al llistat de repositoris del nostre sistema, cal notar que intenta detectar automàticament la versió.
 - `add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`{{execute T1}}
 # Instal·lació de Docker
Finalment actualitzem els repositoris amb les noves entrades i tot seguit instal·lem el programari que conforma l'entorn de Docker:
- `apt update`{{execute T1}}
- `apt install docker-ce docker-ce-cli containerd.io`{{execute T1}}
