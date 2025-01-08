
# API для Yatube

## Описание проекта
API для Yatube — это интерфейс для взаимодействия с социальной сетью Yatube. Он позволяет пользователям создавать публикации, оставлять комментарии, подписываться на других пользователей и ставить лайки. Проект выполнен с использованием Django REST Framework и поддерживает аутентификацию через JWT-токены.

## Основной функционал API:
- Просмотр и создание публикаций
- Оставление комментариев к публикациям
- Подписка на других пользователей
- Поиск по подпискам
- Аутентификация и получение JWT-токена

Документация API доступна по адресу: `http://127.0.0.1:8000/redoc/`

---

## Установка

### Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/ваш_проект/yatube_api.git
cd yatube_api
```

### Создать и активировать виртуальное окружение:
```
python3 -m venv venv
source venv/bin/activate  # Для MacOS и Linux
venv\Scriptsctivate  # Для Windows
```

### Установить зависимости из файла requirements.txt:
```
pip install -r requirements.txt
```

### Выполнить миграции:
```
python manage.py migrate
```

### Запустить проект:
```
python manage.py runserver
```

---
## Права доступа к API:

### Неавторизованным пользователям данные доступны только для чтения:

- **GET** `/api/v1/posts/` — получить список всех публикаций
- **GET** `/api/v1/posts/{id}/` — получить детальную информацию о публикации
- **GET** `/api/v1/groups/` — получить список групп
- **GET** `/api/v1/groups/{id}/` — получить информацию о конкретной группе
- **GET** `/api/v1/posts/{post_id}/comments/` — получить список комментариев к публикации
- **GET** `/api/v1/posts/{post_id}/comments/{id}/` — получить информацию о конкретном комментарии

⚠️ Попытка создать, изменить или удалить данные вернёт ошибку 401 Unauthorized.

### Авторизованные пользователи могут выполнять следующие действия:

- **POST** `/api/v1/posts/` — создать новую публикацию
- **PUT/PATCH/DELETE** `/api/v1/posts/{id}/` — редактировать или удалить свою публикацию
- **POST** `/api/v1/posts/{post_id}/comments/` — добавить комментарий к публикации
- **PUT/PATCH/DELETE** `/api/v1/posts/{post_id}/comments/{id}/` — редактировать или удалить свой комментарий
- **GET/POST** `/api/v1/follow/` — получить список подписок или подписаться на пользователя
- **GET** `/api/v1/follow/?search=username` — искать подписки по имени пользователя

---

## Стек технологий
- Python 3.9+
- Django 4.2
- Django REST Framework
- Djoser + JWT


## Автор


Проект выполнила [Тома Гладышева](https://github.com/tomgllll) в рамках обучения на курсе Яндекс.Практикум.
