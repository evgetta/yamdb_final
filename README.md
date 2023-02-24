![example workflow](https://github.com/evgetta/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

# Проект: CI и CD проекта api_yamdb

Результаты тестовых заданий для Python-разработчиков часто просят отправлять в контейнерах. 
Это делается для того, чтобы человеку, который будет проверять наше тестовое задание, не пришлось настраивать окружение на своём компьютере.

Прошлый проект api_yamdb будет результатом нашего тестового задания, и мы отправим его «вместе с компьютером» — в контейнере, а поможет нам в этом утилита - docker-compose.

Дополнительно мы настроим Continuous Integration и Continuous Deployment, чтобы стал возможен:
 
- автоматический запуск тестов,

- обновление образов на Docker Hub,

- автоматический деплой на боевой сервер при пуше в главную ветку main,

- получение уведомлений об успешном запуске в Telegram.


### Используемые технологии:

Python 3.7 
Django 2.2.16 
Docker 23.0.0 
Docker-compose 1.29.2

### Подготовка удаленного сервера
Установка docker и docker-compose:
- apt install docker.io
  DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
  mkdir -p $DOCKER_CONFIG/cli-plugins
  curl -SL https://github.com/docker/compose/releases/download/v2.16.0/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
  chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose or sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose
  
### Запуск проекта
Выполнить миграции

- docker-compose exec web python manage.py migrate

Создайте суперпользователя

- docker-compose exec web python manage.py createsuperuser

Собрать файлы статики

- docker-compose exec web python manage.py collectstatic --no-input

### После запуска, доступа документация для API, по адресу  

- http://public-server-ip-adress/redoc/


### Автор
Заозерских Евгений
