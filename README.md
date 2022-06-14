# REST API для проекта Yatube

### Описание.

  API_yatube это проект в котором можно обмениваться данными через API
в удобном формате передачи данных JSON.
  В данном проекте настроена аутентификация по JWT-токену. Проект позволяет 
сохранять посты, оставлять комментарии к постам, подписываться на других
авторов, просматривать чужие посты. Удалять, сохранять и изменять может только
автор поста. Просматривать посты или отдельный пост может даже не 
авторизованный пользователь. 

### Технологии.
```
Python 3, Django 2.2 LTS, Django REST Framework, SQLite3, Simple-JWT
```

### Как запустить проект:

- Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Anzhela-Namistyuk/api_final_yatube.git
```

```
cd yatube_api
```

- Cоздать и активировать виртуальное окружение:

```
python3 -m venv venv
```

```
source venv/bin/activate
```

- Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

- Выполнить миграции:

```
python3 manage.py migrate
```

- Запустить проект:

```
python3 manage.py runserver
```

### Примеры запросов к API

Зарегистрировать нового пользователя:

POST запрос

```
http://127.0.0.1:8000/api/v1/users/
```
Передать в поля 

```
{
"username": "string",
"password": "string"
}
```

Получить JWT-токен:

POST запрос

```
http://127.0.0.1:8000/api/v1/jwt/create/
```
Передать в поля 

```
{
"username": "string",
"password": "string"
}
```

Создание публикации:

POST запрос

```
http://127.0.0.1:8000/api/v1/posts/
```

Передать в поля 
(text обязательное поле)

```
{
"text": "string",
"image": "string",
"group": 0
}
```

Получение публикаций:

GET запрос

```
http://127.0.0.1:8000/api/v1/posts/

```

Получение публикации:

GET запрос

```
http://127.0.0.1:8000/api/v1/posts/{id}/
```

Добавление комментария:

POST запрос

```
http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/
```
Передать в поле 

```
{
"text": "string"
}
```
Подписка на автора:

POST запрос

```
http://127.0.0.1:8000/api/v1/follow/
```
Передать в поле 

```
{
"following": "string"
}
```
### Автор.

Анжела Намистюк 