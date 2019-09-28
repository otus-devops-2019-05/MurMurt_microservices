# MurMurt_microservices
MurMurt microservices repository

#### HW: Docker контейнеры (docker-2)

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
