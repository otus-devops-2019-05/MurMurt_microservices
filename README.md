# MurMurt_microservices
MurMurt microservices repository

### HW: Docker контейнеры (docker-2)

- Установили Docker
- Познакомились с основными командами

#### Docker machine
docker-machine - встроенный в докер инструмент для создания хостов и установки на них docker engine

- Создали Docker-хост
- Собрали Dockerfile
- Собрали образ ```docker build -t reddit:latest .```
- Запустили ```docker run --name reddit -d --network=host reddit:latest```
- Запушили образ на docker hub 
    ```docker tag reddit:latest <your-login>/otus-reddit:1.0```
    ```docker push <your-login>/otus-reddit:1.0```


### HW: Docker-образы Микросервисы (docker-3)

- Подключились к ранее созданному Docker host’у ```eval $(docker-machine env docker-host)```
- Создали Dockerfile для каждого сервиса
- Собрали образы ```build.sh```
- Создали сеть и запустили контейнеры ```run.sh```
- Попробовали передавать переменные окружения при запуске контейнеров
- Собрали образ на основе alpine
- Создали Docker volume ```docker volume create reddit_db```
- Запустили образ с volume ```docker run -d --network=reddit --network-alias=post_db \
--network-alias=comment_db -v reddit_db:/data/db mongo:latest```


#### HW: Docker: сети, docker-compose (docker-4)

##### Работа с сетью в Docker
##### Docker-compose
