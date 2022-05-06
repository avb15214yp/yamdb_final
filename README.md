![CI/CD](https://github.com/avb15214yp/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
### Проект api_yamdb

```
API социальной сети с отзывами на фильмы, книги и музыку.
Здесь вы можете зарегистрироваться, чтобы поделиться своим мнением о понравившемся или раздражающем произведении, а ваши друзья смогут прочитать ваш отзыв и оставить к нему комментарии. Также вы можете почитать отзывы об интересующем вас произведении и обсудить их в комментариях с другими пользователями.
Для вежливых граммар-наци есть возможность стать модераторами, чтобы поддерживать чистоту и взаимоуважение на платформе.
```
### Технологии проекта

#### Стек разработки
```
django
nginx
postgres
```

### API

```
Описание в проекте: http://127.0.0.1/redoc/
Тестирование: http://127.0.0.1/api/v1/
```

### Шаблон наполнения env-файла:
env-файл необходимо заполнить следующими значениями:
```
SECRET_KEY=
DB_ENGINE= # указываем, что работаем с postgresql
DB_NAME= # имя базы данных
POSTGRES_USER= # логин для подключения к базе данных
POSTGRES_PASSWORD= # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
```

### Как запустить проект в контейнерах:


```
/infra_sp2/infra$docker-compose up -d --build

/infra_sp2/infra$docker-compose exec web python manage.py migrate
/infra_sp2/infra$docker-compose exec web python manage.py createsuperuser
/infra_sp2/infra$docker-compose exec web python manage.py collectstatic --no-input 
```
### Как заполнить базу данных
```
docker-compose exec web python manage.py shell
>>> from django.contrib.contenttypes.models import ContentType
>>> ContentType.objects.all().delete()
>>> quit()
docker-compose exec web python manage.py loaddata static/fixtures.json
```

Разработчики:

```
https://github.com/Drvmnekta
Пользователи и аутентификация
```

```
https://github.com/JacksonHi
Отзывы и комментарии
```

```
https://github.com/avb15214yp
Произведения и категории
```

Ссылка на сайт: http://avb15214.ddns.net/api/v1/          

(http://51.250.105.190/api/v1/)