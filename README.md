# Docker_Redis_Redis-commander
Rodando Redis com Redis-commande usando container

<h1> As imagens utilizadas nesse projeto forarm? </h1>

<h2> Imagem Redis <h2>
    https://hub.docker.com/_/redis

<img src=./img/DockerHubRedis.png>


<h2> Imagem redis-commandre </h2>
    https://hub.docker.com/r/rediscommander/redis-commander

<img src=./img/redis-commander.png>

<h1> Criando Rede </h1>
    - Comando
        docker network create NetRedis

<img src=./img/network.png>

<h1> Criando Volume </h1>
    - Comando
        docker volume create base_redisDB

<img src=./img/Volume.png>

<h1> Container Redis </h1>

    - Rodando Container

docker container run --name redis -v base_redisDB:/base --network NetRedis -d redis

<img src=./img/ContainerRedis.png>


<h1> Container rdis-commander </h1>
    
    - Rodando Container redis-comander

docker container run --rm --name redis-commander -d -p 8081:8081 --network NetRedis -e REDIS_HOSTS=local:redis:6379 rediscommander/redis-commander:latest

<img src=./img/ContainerRedisCommander.png>



