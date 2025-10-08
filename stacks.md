## STACKS : Docker Compose dans Swarm 📡:


### Commandes Stack:
- Déployer une stack
```
docker stack deploy -c docker-stack.yml myapp
```
- Lister les stacks
```
docker stack ls
```
- Lister les services d'une stack
```
docker stack services myapp
```
- Supprimer une stack
```
docker stack rm myapp
```



### Configuration d'un fchier .yml pour le stack
- ex : stack.yml

```
version: '3.8'
services:
  web:
    image: nginx
    ports:
      - "80:80"
    deploy:
      replicas: 3
      resources:
        limits:
          memory: 128M
        reservations:
          memory: 64M
      restart_policy:
        condition: on-failure
  db:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_PASSWORD: secret
    deploy:
      replicas: 1
      placement:
        constraints: [node.role == manager]
```
