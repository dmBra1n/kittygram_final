# Kittygram

![](https://github.com/dmBra1n/kittygram_final/actions/workflows/main.yml/badge.svg)

## Описание проекта

Kittygram — социальная сеть для обмена фотографиями любимых питомцев.<br>
Проект состоит из бэкенд-приложения на Django и фронтенд-приложения на React.

Приложение позволяет: 
- зарегистрироваться и авторизоваться пользователю
- добавить нового котика на сайт или изменить существующего
- посмотреть записи других пользователей

Проект написан в рамках учебного курса "Python-разработчик" от Yandex.Practicum.<br>
Основные задачи бали: 
- развернуть фронтэнд и бэкэнд на облачном сервере используя Docker
- настроить автоматизацию деплоя CI/CD

## Технологии
- Python
- Django
- Django REST Framework
- Simple JWT
- Gunicorn 20.1.0
- React (фронтенд-приложение)
- Docker
- CI/CD
- GitHub Actions

## Локальный запуск проекта
1. Склонировать репозиторий
2. В корне проекта создать и прописать файл _.env_
  
    ```
    POSTGRES_USER=<имя_пользователя_БД>
    POSTGRES_PASSWORD=<пароль_БД>
    POSTGRES_DB=<имя_БД>
    DB_PORT=<порт_соединения_к_БД>
    DB_HOST=db
    
    SECRET_KEY=<django_secret_key>
    ```
3. В теменале, в корне проекта выполнить команду `docker compose up -d`
4. Вполнить миграции и собрать статику:
     ```
     docker exec backend python manage.py migrate
     docker compose exec backend python manage.py collectstatic
     docker compose exec backend cp -r /app/collected_static/. /backend_static/static/  
     ```
Сервер будет доступен по адресу: http://localhost:9000/

  ## Автор
Вадим Миронов - [ссылка на GitHub](https://github.com/dmBra1n)
