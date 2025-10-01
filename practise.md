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

# Supprimer un conteneur
docker rm mon-conteneur

# Supprimer un conteneur actif
docker rm -f mon-conteneur



