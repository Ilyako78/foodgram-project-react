### Описание
Проект Foodgram собирает рецепты.


### Ссылка на документцию

http://localhost/api/docs/


### Стек технологий
Python 3.7

Django REST framework

Django ORM

Git

Djoser

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


