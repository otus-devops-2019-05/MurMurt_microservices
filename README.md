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


### HW: Docker: сети, docker-compose (docker-4)

##### Работа с сетью в Docker
- Разобрались с работой сети в Docker
- Создали bridge-сеть в docker 
##### Docker-compose

- Установили docker-compose на локальную машину
- Собрали образы приложения reddit с помощью docker-compose
- Запустить приложение reddit с помощью docker-compose

Q: Узнайте как образуется базовое имя проекта. Можно ли его задать? Если можно то как? 
A: Дефолтное значение - имя директории с docker-compose.yml. Можно задать используя переменную окружения COMPOSE_PROJECT_NAME


### HW: Устройство Gitlab CI. Построение процесса непрерывной поставки (gitlab-ci-1)

- Создал виртуальную машину (руками в ui)
- Установил docker на хост через ansible
- Запустил Gitlab CI
- Настроил Gitlab CI
- Создал CI/CD Pipeline
- Настроил Runner для запуска pipeline (нужен токен)
- Добавил окружения


### HW: Введение в мониторинг

- Создал докер-хост в GCP
- Запустил и протестировал образ prometeus.
- Создал docker-compose файл с prometeus
- Образы запушил на docker-hub https://cloud.docker.com/u/igataullin/repository/list
- Добавил job node_exporter для отдачи метрик prometeus


### Мониторинг приложения и инфраструктуры
 - Мониторинг контейнеров
 - Сбор и визуализациция метрик
 - Алертинг: настройка, проверка.

  URL к проектам https://cloud.docker.com/u/igataullin/repository/list


### Логирование и распределенная трассировка

- Сбор неструктурированных логов
- Визуализация логов
- Сбор структурированных логов
- Распределенная трасировка