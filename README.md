# YaMDb в Docker compose

***[YaMDb](https://github.com/pozarnik/yamdb_api) - API проект, собирающий отзывы пользователей на различные произведения***API проект, собирающий отзывы пользователей на различные произведения***

## Возможности проекта

- Свободная регистрация пользователей
- Получение токена с помощью кода, высылаемого на почту при регистрации
- Система ролей пользователя (*user, moderator, admin*)
- Добавление различных жанров и категорий произведений
- Добавление произведений, с возможностью выбора категории и нескольких жанров
- Публикация отзывов к произведениям
- Публикация комментариев к отзывам

## Технологии

- Python 3.9
- Django 3.2
- Django REST framework 3.12.4
- PostgreSQL 13.0
- Gunicorn 20.0.4
- nginx 1.21.3

## Установка и запуск проекта в Docker

Скопируйте проект и перейдите в папку __infra__

```sh
git clone https://github.com/pozarnik/yamdb_api_docker.git
cd yamdb_api_docker/infra/
```

В папке __infra__ создайте файл __.env__, добавьте в него свои данные при необходимости (без пробелов и комментариев):

```
SECRET_KEY=            # ключ для генерации хэша Django
DEBUG=                 # значение Debug
DB_ENGINE=             # укажите используемую БД
DB_NAME=               # имя базы данных
POSTGRES_USER=         # логин для подключения к БД
POSTGRES_PASSWORD=     # пароль для подключения к БД (установите свой)
DB_HOST=               # название сервиса (контейнера) БД
DB_PORT=               # порт для подключения к БД 
EMAIL_HOST=            # адрес сервера исходящей почты
EMAIL_PORT=            # порт сервера исходящей почты
EMAIL_HOST_USER=       # логин для авторизации на почтовом сервере
EMAIL_HOST_PASSWORD=   # пароль для авторизации на почтовом сервере
```

Запустите docker-compose

```sh
sudo docker-compose up -d --build
```

Выполните миграции и создайте суперпользователя

```sh
sudo docker-compose exec web python manage.py migrate
sudo docker-compose exec web python manage.py createsuperuser
```

Переместите файлы статики

```sh
sudo docker-compose exec web python manage.py collectstatic --no-input
```

Остановка docker-compose и удаление всех созданных Docker папок и томов проекта

```sh
sudo docker-compose down -v
```

## Документации проекта

При запущенном проекте перейдите по одному из адресов в браузере

```sh
http://localhost/redoc/
http://localhost/swagger/
```
## Мои профили

- [GitHub](https://github.com/pozarnik/)
- [LinkedIn](https://www.linkedin.com/in/alekseyevich-ivan/)

## License

MIT


