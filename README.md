# **Yatube API**

API для социальной сети Yatube с возможностью публикации постов, комментариев и подписки на авторов.

---
## **Основные возможности**

- Создание и управление публикациями

- Комментирование публикаций

- Подписка на других пользователей

- Группировка публикаций по сообществам

- JWT-аутентификация

---  
## **Технологии**

- Python 3.9

- Django 3.2

- Django REST Framework 3.12

- Simple JWT

- SQLite (для разработки)

---
## **Установка**

1. Клонируйте репозиторий:
```bash
git clone https://github.com/markovsky1/api_final_yatube.git
```

2. Создайте и активируйте виртуальное окружение:

```bash
python -m venv venv
source venv/bin/activate  # Linux/MacOS
venv\Scripts\activate     # Windows
```
    
3. Установите зависимости:
    
```bash
pip install -r requirements.txt
```
    
4. Примените миграции:
    
```bash
python manage.py migrate
```
    
5. Запустите сервер:
    
```bash
python manage.py runserver
```
    
---
## **Документация API**

После запуска сервера документация будет доступна по адресу: [Redoc](http://127.0.0.1:8000/redoc/)

---

## **Примеры запросов**

- ### Получение JWT-токена

```
POST /api/v1/jwt/create/
Body: {"username": "ваш_username", "password": "ваш_пароль"}
```

- ### Создание публикации
```
POST /api/v1/posts/
Headers: Authorization: Bearer <ваш_токен>
Body: {"text": "Текст публикации", "group": 1}
```

- ### Получение списка публикаций

```
GET /api/v1/posts/
```

- ### Создание подписки

```
POST /api/v1/follow/
Headers: Authorization: Bearer <ваш_токен>
Body: {"following": "username_автора"}
```

