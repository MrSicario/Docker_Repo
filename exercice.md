## exerice 1:
```
1) trouver different image:
    docker search [images]

2) telecharger:
    docker pull [images]

3) lancer un conteneur: 
    docker run --name [name] [images:version_ou_images]

4) demarrer le conteneur:
    docker start [id_ou_nom_conteneur]

5) interagir avec conteneur: 
    docker exec -it [nom_coteneur] bash
```



## exercice 2:
```
1) cree et lancer le conteneur mais aussi interagir avec:
docker run -it --name [nom_conteneur] [images] 

2) lister les conteneurs:
docker ps ou ps -a

3) creer et lancer et supp automatique le conteneur:
docker run -it --rm --name [nom_conteneur] [images]
```
