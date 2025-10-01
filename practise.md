# 🛠️ Docker - Pratique et Commandes
>  ⛔ Veuillez voir la page d'installation avant de voir la pratique 
<hr>

<div align="center">" 💡 La meilleure façon d'apprendre est de pratiquer "</div> 

## Pour voir la liste des dommandes docker 
```
docker --help 
```


## Commandes de base
.Avant toute chose , vérifiez si le service de  Docker tourne
```
systemctl status docker
```
.Pour le demarer
```
systemctl start docker
```
.Pour l'arreter 
```
systemctl stop docker
```

### Gestion des conteneurs
```
# Créer et de démarrer un nouveau conteneur Docker basé sur l' nginx image
docker run nginx:latest

# Lancer un conteneur
docker run -d --name mon-conteneur nginx

# Voir les conteneurs en cours
docker ps

# Voir tous les conteneurs (même arrêtés)
docker ps -a

# Arrêter un conteneur
docker stop mon-conteneur

# Arreter un conteneur en cours
docker stop IDconteneur

# Redémarrer un conteneur
docker restart mon-conteneur

# Supprimer un conteneur
docker rm mon-conteneur

# Supprimer un conteneur actif
docker rm -f mon-conteneur

# Voir les logs d'un conteneur
docker logs mon-conteneur
```

### Gestion d'image
```
# Creer une image:
docker build -t nomimage 

# Supprimer une images
doker rmi monimage

# Télécharger une image
docker pull nginx:latest

# Lister les images locales
docker images

# Construire une image depuis un Dockerfile
docker build -t mon-image .

# Interface graphique pour gérer Docker et son image :
docker volume create portainer_data
docker run -d -p 9000:9000 \
  --name=portainer \
  --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce

# Lancer l'image avec cette interface
docker run -p 9000:9000 nomImage

# Pour accéder à L'image ( ouvrir un navigateur et taper le lien si dessous ) 
http://localhost:9000







