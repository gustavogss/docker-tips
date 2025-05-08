# DOCKER TIPS

- Dicas e comandos usados para docker e docker-compose

  ## Instalação e Configuração do Docker e Docker-Compose :

  - Desinstale versões anteriores:
     ```
     sudo apt-get remove docker* containerd runc
     ```
   - Instale dependências iniciais:
     ```
      sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
     ```
   - Adicione a chave pública:
     ```
     curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
     ```
   - Adicone o repositório remoto no apt:
     ```
     echo \
     "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" \  |  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null  
     ```    
   - Atualize os pacotes:
     ```
     sudo apt-get update
     ```
   - Instale as últimas versões:
     ```
     sudo apt-get install docker-ce docker-ce-cli containerd.io
     ```
   - Adicione seu usuário ao grupo de usuários Docker
     ```
     sudo groupadd docker
     ```
   - Adicione seu usuário a este novo grupo
     ```
     sudo usermod -aG docker $USER
     ```
   - Ative as alterações realizadas nos grupos
     ```
     newgrp docker
     ```
   - Verifique o status do docker
     ```
     sudo systemctl status docker
     ```
   - Habilite o daemon do Docker para iniciar durante o boot:
     ```
     sudo systemctl enable docker
     ```
   - Instale o Docker Compose:
     ```
     sudo curl -L "https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
     ```
   - Permissão de execução para o Docker compose:
     ```
     sudo chmod +x /usr/local/bin/docker-compose
     ```
   - Verifique a versão do Docker Compose:
     ```
     docker-compose --version
     ```

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