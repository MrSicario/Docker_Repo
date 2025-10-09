# Exemple de Swarm complet 👇🏾
- Deployement d'application web

docker network create -d overlay web-network
### Déployer le service web
```
docker service create --name webapp \
  --network web-network \
  --replicas 3 \
  -p 80:80 \
  nginx
```

### Déployer la base de données
```
docker service create --name database \
  --network web-network \
  --replicas 1 \
  -e MYSQL_ROOT_PASSWORD=secret \
  mysql:8.0
```
- Stack complète:
# docker-stack.yml
```
version: '3.8'
services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
    deploy:
      replicas: 3
      update_config:
        parallelism: 2
        delay: 10s
      rollback_config:
        parallelism: 1
        delay: 5s
      resources:
        limits:
          cpus: '0.50'
          memory: 512M
        reservations:
          cpus: '0.25'
          memory: 256M
      restart_policy:
        condition: on-failure
        delay: 5s
        max_attempts: 3
        window: 120s
    networks:
      - webnet

  visualizer:
    image: dockersamples/visualizer:latest
    ports:
      - "8080:8080"
    volumes:
      - "/var/run/docker.sock:/var/run/docker.sock"
    deploy:
      placement:
        constraints: [node.role == manager]
    networks:
      - webnet

networks:
  webnet:
    driver: overlay
```
