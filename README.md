https://github.com/evgetta/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg

# Проект: запуск docker-compose

Результаты тестовых заданий для Python-разработчиков часто просят отправлять в контейнерах. 
Это делается для того, чтобы человеку, который будет проверять наше тестовое задание, не пришлось настраивать окружение на своём компьютере.

Прошлый проект api_yamdb будет результатом нашего тестового задания, и мы отправим его «вместе с компьютером» — в контейнере, а поможет нам в этом утилита - docker-compose.

### Используемые технологии:

Python 3.7 
Django 2.2.16 
Docker 23.0.0 
Docker-compose 1.29.2

### Запуск проекта в  Docker контейнере
Перейти в раздел infra для сборки docker-compose, и прописать

- docker-compose up (ключ -d для "фонового режима")

Выполнить миграции

- docker-compose exec web python manage.py migrate

Создайте суперпользователя

- docker-compose exec web python manage.py createsuperuser

Собрать файлы статики

- docker-compose exec web python manage.py collectstatic --no-input

Для загрузки резервной копии

- docker-compose exec web python manage.py loaddata fixtures.json

### После запуска, доступа документация для API, по адресу  

- http://localhost/redoc/

### Автор
Заозерских Евгений
