# 🛠️ Docker - Pratique Avancer
<hr>
<div align="center">
  
### lancer un conteneur et interagir avec conteneur  
```
docker run -it --name [name du contenneur] [image]  
```
### lancer un conteneur et le supprimer automatiquement   
```
docker run -it --rm --name [name du conteneur] [image]  
 exit dans le terminal ferme le conteneur et il sera supprimer par [rm]  
```
### redemarrer le conteneur:   
```
docker start [name du conteneur]
```
### Exécuter des commandes dans un conteneur actif:  
```
 docker exec –t –i [id ou conteneur] bash    
 docker exec -it [id ou conteneur] "bash meme chose"  
```
### voir la configuration du conteneur ou inspecter configuration du conteneur:  
```
docker inspect [name conteneur]  
```
### voir info sur docker:  
```
docker info  
```
### recherche d'image (necessite un compte dockerhub):  
```
docker search [nom image] --> ex: nginx ou ubuntu  
    -ensuite telecharger l'images:  
docker pull [nom d image que tu as trouver]  
```
### importer ou construire images via dockerfile:  
```
docker build –t [image] [chemin   dockerfile] ""necessite un dockerfile""  
```
### Afficher l’historique d’une image  
```
docker history [image]  
```
### Visualiser les logs d’un conteneur (les 5 derniéres lignes)  
```
docker logs –-tail 5 [conteneur]
```
### VOLUMES (Storage):
```
docker volume create mon-vol    # Créer un volume
docker volume ls                # Liste les volumes
docker run -v mon-vol:/data nginx
```
### DOCKERFILE:
```
FROM node:14-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```
### Build d'image:
```
docker build -t mon-app .          # Construit une image Docker personnalisée
docker build -t mon-app:1.0 .     # Avec tag
```
### DOCKER COMPOSE:
```
version: '3.8'
services:
  web:
    image: nginx
    ports: ["80:80"]
  db:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_PASSWORD: secret
```
### Commandes Compose:
```
docker-compose up -d        # Démarre les services
docker-compose down         # Arrête les services
docker-compose ps           # Statut du service
```
### Gestion des SERVICES:
```
# Créer un service
docker service create --name web -p 80:80 nginx
# Service avec réplicas
docker service create --name web --replicas 3 -p 80:80 nginx
# Lister les services
docker service ls
# Inspecter un service
docker service inspect web
# Voir les tâches d'un service
docker service ps web
# Mettre à jour un service
docker service update --replicas 5 web
# Scale un service
docker service scale web=10
# Supprimer un service
docker service rm web
```
### Commandes Stack:
```
# Déployer une stack
docker stack deploy -c docker-stack.yml myapp
# Lister les stacks
docker stack ls
# Lister les services d'une stack
docker stack services myapp
# Supprimer une stack
docker stack rm myapp
```

### Commandes de MAINTENANCE:
```
# Mettre à jour un service
docker service update --image nginx:latest web
# Rollback d'un service
docker service rollback web
# Pause/resume de service
docker service update --update-pause web
docker service update --update-resume web
```
### Optimisation 

- Limiter les ressources
```
docker run --memory=512m --cpus=1.0 nginx
```
### Sécurité:
- Exécuter en non-root
```
docker run --user 1000:1000 nginx
```
### Docker Hub:
```
docker login                  # Connexion
docker tag app user/app       # Tagger
docker push user/app          # Publier
```
### Nettoyage:
```
#Nettoyage complet:
docker system prune -a
# Nettoyage sélectif:
docker container prune    # Containers arrêtés
docker image prune        # Images non utilisées
docker volume prune       # Volumes non utilisés
```
</div>
