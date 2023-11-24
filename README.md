# **API YA:accessibility:UBE**

### Описание:

API для YaTube представляет собой проект в котором реализованы такие возможности как: создание, чтетие записей и добавление комментариев к ним, а также их редактирование, способность оформления подписок и отслеживание своих подписчиков.

### Используемые технологии:
* Python
* Django REST Framework
* Simple JWT + Djoser

### Как запустить проект:

* Клонировать репозиторий и перейти в него в командной строке:

  ```
  git clone https://github.com/AndreyLeshchev/api_final_yatube.git
  ```
  ```
  cd api_final_yatube
  ```

* Cоздать и активировать виртуальное окружение:

  ```
  python -m venv venv
  ```
  ```
  source venv/Scripts/activate
  ```

* Установить зависимости из файла requirements.txt:

  ```
  python -m pip install --upgrade pip
  ```

  ```
  pip install -r requirements.txt
  ```

* Выполнить миграции:

  ```
  python manage.py migrate
  ```

* Запустить проект:

  ```
  python manage.py runserver
  ```
  
* После запуска проекта будет доступна документация по адресу:

  ```
  http://127.0.0.1:8000/redoc/
  ```

### Примеры запросов к API:

* Для получение специального токена необходимо отправить запрос по адресу:

  > POST http://127.0.0.1/api/v1/jwt/create/
  
  Пример запроса:

  ```
  {
    "username": "user",
    "password": "password"
  }
  ```
* Для получения всех записей необходимо отправить запрос по адресу:
  
  > GET http://127.0.0.1:8000/api/v1/posts/

  Пример ответа:
  
  ```
  {
      "count": 123,
      "next": "http://api.example.org/accounts/?offset=400&limit=100",
      "previous": "http://api.example.org/accounts/?offset=200&limit=100",
      "results": [
          {
              "id": 0,
              "author": "string",
              "text": "string",
              "pub_date": "2021-10-14T20:41:29.648Z",
              "image": "string",
              "group": 0
          }
      ]
  }
  ```

* Для получения комментариев к посту необходимо отправить запрос по адресу:

  > GET http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/{id}/
  
  Пример ответа:
    
  ```
  [
      {
           "id": 0,
           "author": "string",
           "text": "string",
           "created": "2019-08-24T14:15:22Z",
           "post": 0
       }
   ]
