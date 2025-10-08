## Docker Network  🛜


La commande network  

1. lister network ou les reseaux:  
```
docker network ls  
```

2. tester disponinilite reseau:  
```
docker run -it --network=none  [image]
```
Ici on a des conteneur isoler (sans reseau connecter)
remaque : le conteneur doit pouvoir faire 'ip '

3. Creer un reseau:
```
docker network create --driver=bridge [name_reseau]  
```

4. creer et relier un conteneur a un reseau:
```
docker run -it --name [name] --network=[name_reseau] [images]
```

5. relier un conteneur existant au reseau:  
```
docker network connect [name_reseau] [name_conteneur_existant]
```

6. verifier le conteneur relier a un reseau: 
```
docker network inspect 
```

7. deconnetcer un conteneur a un reseau: 
```
docker network disconnect [name_reseau] [name_conteneur]
```

8. supprimer reseau: 
```
docker network rm [name_reseau]
```
