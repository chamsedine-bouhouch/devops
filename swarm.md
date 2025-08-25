# Swarm

## Activate swarm in docker

swarm is inactive by default
check with

```sh
docker info

```

### init

```sh

docker swarm init

```

new available commands

- docker node
- docker service
- docker

```sh
docker service create alpine ping 8.8.8.8
docker service update <service_id> --replicas 3
```
