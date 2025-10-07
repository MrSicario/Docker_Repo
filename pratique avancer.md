

<div align="center">
  
## lancer un conteneur et interagir avec conteneur  
```
docker run -it --name [name du contenneur] [image]  
```
## lancer un conteneur et le supprimer automatiquement   
```
docker run -it --rm --name [name du conteneur] [image]  
 exit dans le terminal ferme le conteneur et il sera supprimer par [rm]  
```
## redemarrer le conteneur:   
```
docker start [name du conteneur]
```
## Exécuter des commandes dans un conteneur actif:  
```
 docker exec –t –i [id ou conteneur] bash    
 docker exec -it [id ou conteneur] "bash meme chose"  
```
## voir la configuration du conteneur ou inspecter configuration du conteneur:  
```
docker inspect [name conteneur]  
```
## voir info sur docker:  
```
docker info  
```
## recherche d'image (necessite un compte dockerhub):  
```
docker search [nom image] --> ex: nginx ou ubuntu  
    -ensuite telecharger l'images:  
docker pull [nom d image que tu as trouver]  
```
## importer ou construire images via dockerfile:  
```
docker build –t [image] [chemin   dockerfile] ""necessite un dockerfile""  
```
## Afficher l’historique d’une image  
```
docker history [image]  
```
## Visualiser les logs d’un conteneur (les 5 derniéres lignes)  
```
docker logs –-tail 5 [conteneur]
```

</div>
