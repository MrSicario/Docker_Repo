# 🐳 Docker - Cours et Connaissances

## 1. Qu'est-ce que Docker ?

### Définition
Docker est une plateforme de conteneurisation qui permet de créer, déployer et exécuter des applications dans des conteneurs.

### Avantages Principaux
- **Isolation** : Chaque application tourne dans son environnement
- **Portabilité** : Fonctionne de la même façon sur tous les systèmes
- **Légèreté** : Partage le noyau du système hôte
- **Rapidité** : Démarrage en quelques secondes

### Différence avec les Machines Virtuelles
| Docker (Conteneurs) | Machines Virtuelles |
|---------------------|---------------------|
| Partage le noyau OS | Noyau OS dédié |
| Démarrage rapide | Démarrage lent |
| Faible consommation | Consommation élevée |
| Isolation processus | Isolation complète |

## 2. Concepts Clés

### Image Docker
- Modèle **read-only** pour créer des conteneurs
- Empilement de couches (layers)
- Exemple : `nginx`, `mysql`, `python`

### Container
- **Instance d'exécution** d'une image
- Environnement isolé et éphémère
- Peut être démarré, arrêté, supprimé

### Dockerfile
- Fichier texte contenant les instructions pour construire une image
- Définit l'environnement d'exécution
- Best practices : minimiser le nombre de layers

### Docker Hub
- Registry public d'images Docker
- Contient des images officielles et communautaires
- Alternative : Docker Registry privé

## 3. Architecture Docker

### Composants Principaux
1. **Docker Daemon** : Processus background qui gère les conteneurs
2. **Docker Client** : Interface en ligne de commande
3. **Docker Registry** : Stockage et distribution d'images

### Flux de Travail
1. Le client envoie une commande au Daemon
2. Le Daemon télécharge l'image depuis le Registry
3. Le Daemon crée et exécute le conteneur

## 4. Écosystème Docker

### Outils Associés
- **Docker Compose** : Orchestration multi-conteneurs
- **Docker Swarm** : Orchestration de cluster
- **Docker Desktop** : Interface graphique
- **Kubernetes** : Orchestration avancée

## 5. Cas d'Usage

### Développement
- Environnements reproductibles
- Pas de "ça marche sur ma machine"
- Intégration continue

### Production
- Déploiement scalable
- Isolation des services
- Rollback facile

---

*Document en cours d'enrichissement...*
