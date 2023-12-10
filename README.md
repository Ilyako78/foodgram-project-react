### Описание
Проект Foodgram собирает рецепты.
Позволяет формировать список покупок.


### Стек технологий

Python 3.9

Django REST framework

Django ORM

Docker

Gunicorn

nginx

PostgreSQL

Git

### Шаблон файла .env

DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql

DB_NAME= # имя базы данных

POSTGRES_USER= # логин для подключения к базе данных

POSTGRES_PASSWORD= # пароль для подключения к БД (установите свой)

DB_HOST=db # название сервиса (контейнера)

DB_PORT=5432 # порт для подключения к БД

SECRET_KEY # Секретный ключ проекта


### Скоприовать файлы на сервер

scp docker-compose.yml nginx.conf .env fixtures.json user@ip:/home/user/

### Запуск проекта 


docker-compose up -d --build

docker-compose exec web python manage.py migrate

docker-compose exec web python manage.py createsuperuser

docker-compose exec web python manage.py collectstatic --no-input

### Сделать резервную копию

docker-compose exec web python manage.py dumpdata > fixtures.json

### Восстановить из резервной копии

Список контейнеров

sudo docker container ls 

docker cp fixtures.json <имя контейнера>:app/

docker-compose exec web python manage.py loaddata fixtures.json

### Заполнить БД ингридиентами

docker-compose exec web python3 manage.py upload_db

## Примеры
Полная спецификация api
```
/api/docs/
```

Получить токен 
```
/api/auth/token/login/
```

Получение списка рецептов
```
/api/recipes/
```

Получение списка ингридиентов
```
/api/ingredients/
```

Загрузить список ингридиентов из csv файла:
```
python3 manage.py upload_db
```

Восстановить данные в БД из дампа
```
python manage.py loaddata fixtures.json
```

## Авторы

https://github.com/Ilyako78


