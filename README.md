# YaMDb

***API проект, собирающий отзывы пользователей на различные произведения***

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
- etc.

## Установка и запуск проекта

Скопируйте проект и создайте виртуальное окружение

```sh
git clone https://github.com/pozarnik/api_yamdb.git
cd api_yamdb
python -m venv venv
```

Активируйте виртуальное окружение и установите зависимости

```sh
source venv/Scripts/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Выполните миграции

```sh
cd api_yamdb
python manage.py makemigrations
python manage.py migrate
```

В корне проекта создайте файл _.env_, добавьте в него следующие строки со своими данными:

```
EMAIL_HOST =
EMAIL_PORT =
EMAIL_HOST_USER =
EMAIL_HOST_PASSWORD =
```

Запустите проект

```sh
python manage.py runserver
```

## Документации проекта

Запустите сервер и перейдите по адресу

```sh
http://127.0.0.1:8000/redoc/
http://127.0.0.1:8000/swagger/
```

## Мои профили

- [GitHub](https://github.com/pozarnik/)
- [LinkedIn](https://linkedin.com/in/pozarnik/)

## License

MIT


