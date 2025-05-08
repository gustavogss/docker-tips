# DOCKER TIPS
- Dicas e comandos usados para docker e docker-compose

### Instalando uma imagem:
```
docker-compose up -d
```
### Removendo uma imagem:
```
docker-compose down
```
### Parar e remover todos os containers:
```
docker stop $(docker ps -aq)
docker rm $(docker ps -aq)
```
### Remover todas as imagens:
```
docker rmi $(docker images -q)
```
### Remover todos os volumes não utilizados:
```
docker volume rm $(docker volume ls -q)
```
### Remover todas as redes não utilizadas:
```
docker network prune -f
```
### Limpar tudo:
```
docker system prune -af --volumes
```

## GitLab: