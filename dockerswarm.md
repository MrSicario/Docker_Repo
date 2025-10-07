## 💥 Docker swarm:  

C'est un groupe de machines executant le moteur Docker et faisant partie du meme cluster.

- elle est composer de:

-> composer: avec le fichier .yml et du docker CLI

-> Swarm: les machines worker. 

-> cluster: les machine qui executer les commandes appeler manager.

## 🎛️ Commande en docker Swar  
# Creer un cluster swarm 
- Initier le mode swarm:
```
 docker swarm init  
 docker swarm  init --advertise-addr (adresse ip)
```

- Verifier l'etat du swarm:
```
docker info 
docker node ls
```

- Ajouter des noeuds au swarm (worker):  
```
docker swarm join --token (notre token de worker) (adresse ip):(port)
```
- Noued(manager):  
```
 docker swarm join --token (token manager) (adresse ip):port
```
- Pour voir les details:  
 ```
docker node ls
```
<hr>

# Deployement  :
 Prerequis 🛄:
 - Creeation du dossier avec Dockerfile , builder sois meme son images et l'implementer dans fichier .yml
```
build l images
docker init
docket stack deploy -c fichier.yml [nom_du_dossier_project]
```
- Ensuite deployer 💥
```
docket stack deploy -c fichier.yml [nom_du_dossier_project]
```
- Arreter definitive ou supprimer un stack:
```
docker stack rm [nom_du_dossier_project]
```
- Verifier stack:
```
docker stack ls
```
- Verfier service d'un stack:
``` 
docker stack services [nom_du_dossier_project]
```
- Etat services (tres important pour verfier les replicas qui crash ou pas):
```
docker service ps [nom_du_dossier_project]
```
- Mise a jour d un service:
```
-- docker service update --force [nom_du_dossier_project] 
```
