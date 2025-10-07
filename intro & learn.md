# 🐳 Docker - Cours et Connaissances

## 1. Qu'est-ce que Docker ? A quoi sert t-il ? Ses Avantages ...

### Définition
Docker est une plateforme de conteneurisation ouverte pour le développement, la livraison ou le déployement et l'exécution d'applications dans des conteneurs.

### À quoi peut me servir Docker ?
Livraison rapide et cohérente de vos applications ( permet aux développeurs de travailler dans des environnements standardisés à l'aide de conteneurs locaux)

Déploiement et mise à l'échelle réactifs (  permet une grande portabilité des charges de travail ) 

Exécuter davantage de charges de travail sur le même matériel ( permett d'optimiser la capacité de votre serveur pour atteindre vos objectifs métier )

### Avantages Principaux ✅
- **Isolation** : Chaque application tourne dans son environnement
- **Portabilité** : Fonctionne de la même façon sur tous les systèmes
- **Légèreté** : Partage le noyau du système hôte
- **Rapidité** : Démarrage en quelques secondes.



## 2. Concepts Clés

### Image Docker
- Modèle **read-only** , modèle autonome et immuable, en lecture seule, contenant tout le code, les bibliothèques, les dépendances et les configurations nécessaires pour exécuter une application. ( Création de conteneurs ) 
- Empilement de couches (layers)
- Exemple : `nginx`, `mysql`, `python`

### Container
- **Instance d'exécution** d'une image , autonome qui regroupe une application et toutes ses dépendances (code, bibliothèques, outils système) dans un format standardisé pour un déploiement rapide et fiable sur n'importe quel environnement.
- Environnement isolé et éphémère
- Peut être démarré, arrêté, supprimé

⛔ A savoir : 
Pour avoir des conteneurs ,il faut d'abord avoir des images de base pour le conteneur.(on peut trouver les images sur dockehub).

### Dockerfile
- Fichier texte contenant les instructions pour construire une image , grâce à ce fichier que vous allez pouvoir automatiser la création d'une image
- Définit l'environnement d'exécution
- Best practices : minimiser le nombre de layers

### Docker Hub
- Registry public d'images Docker , offrant un vaste catalogue d'images préconstruites et la possibilité pour les développeurs de partager leurs propres images dans des dépôts publics ou privés
- Contient des images officielles et communautaires
- Alternative : Docker Registry privé

### Docker Volume 
- un mécanisme de stockage persistant pour les conteneurs, permettant aux données de survivre même après la suppression d'un conteneur
-  garantit que les données critiques, comme celles d'une base de données, ne sont pas perdues et peuvent être facilement partagées entre les conteneurs ou déplacées vers d'autres hôtes ..

### Docker Network 
- mécanisme qui définit et gère des zones de communication pour les conteneurs Docker
- permettant d'échanger des données entre eux, avec la machine hôte et des services externes ..


## 3. Architecture Docker

### Composants Principaux
1. **Docker Daemon** : Processus background qui gère les conteneurs...( dockerd) écoute les requêtes de l'API Docker et gère les objets Docker tels que les images, les conteneurs, les réseaux et les volumes
2. **Docker Client** : Interface en ligne de commande... (docker) est le principal moyen par lequel de nombreux utilisateurs interagissent avec Docke
3. **Docker Registry** : Stockage et distribution d'images...

### Flux de Travail
1. Le client envoie une commande au Daemon
2. Le Daemon télécharge l'image depuis le Registry
3. Le Daemon crée et exécute le conteneur....

## 4. Écosystème Docker

### Outils Associés
- **Docker Compose** : Orchestration multi-conteneurs , un outil qui permet de définir, gérer et exécuter des applications complexes composées de plusieurs conteneurs Docker en utilisant un seul fichier de configuration YAML
- **Docker Swarm** : Orchestration de cluster , n outil d'orchestration de conteneurs intégré à Docker, qui permet de regrouper plusieurs hôtes Docker dans un seul cluster virtuel, un "Swarm
- **Docker Desktop** : Interface graphique de Docker 
- **Kubernetes** : Orchestration avancée , plateforme permettant d'exécuter et de gérer des conteneurs à partir de nombreux systèmes d'exécution de conteneurs

## 5. Cas d'Usage

### Développement
- Environnements reproductibles
- Pas de "ça marche sur ma machine seulement"
- Intégration continue

### Production
- Déploiement scalable..
- Isolation des services
- Rollback facile..

### Différence avec les Machines Virtuelles
| Docker (Conteneurs) | Machines Virtuelles |
|---------------------|---------------------|
| Partage le noyau OS | Noyau OS dédié |
| Démarrage rapide | Démarrage lent |
| Faible consommation | Consommation élevée |
| Isolation processus | Isolation complète |

