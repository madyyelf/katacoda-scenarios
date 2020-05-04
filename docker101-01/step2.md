# Execució del "Hello World!" de Docker
## Mètode pas a pas
Per executar el contenidor "Hello World!" podriem:
- Cecar-lo a Docker Hub amb `docker search hello-world`{{execute T1}}
- Descarregar-lo amb `docker pull hello-world`{{execute T1}}
- I finalment executar-lo amb `docker run hello-world`{{execute T1}}
## Mètode ràpid
Però Docker intenta facilitar la vida, per tant tan sols fent `docker run hello-world`{{execute T1}} ja ens fa automàticament els tres passos: busca una coincidència exacte a Docker Hub, descarrega l'imatge i genera un contenidor.
