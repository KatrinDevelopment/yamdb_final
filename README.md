# REST API для Yatube

![Status](https://github.com/KatrinDevelopment/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

## Описание проекта

Проект YaMDb собирает отзывы пользователей на произведения. Сами произведения
в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
Добавлять произведения, категории и жанры может только администратор.
Произведения делятся на категории, такие как «Книги», «Фильмы», «Музыка».
Произведению может быть присвоен жанр из списка предустановленных (например,
«Сказка», «Рок» или «Артхаус»).

Пользователи оставляют к произведениям текстовые отзывы и ставят произведению
оценку в диапазоне от одного до десяти (целое число); из пользовательских
оценок формируется усреднённая оценка произведения — рейтинг (целое число).
На одно произведение пользователь может оставить только один отзыв.
Пользователи могут оставлять комментарии к отзывам.

Добавлять отзывы, комментарии и ставить оценки могут только аутентифицированные
пользователи.

## Ресурсы API YaMDb

Ознакомьтесь с нашей документацией, чтобы узнать, что доступно в API и как его
использовать в репозитории `yatube_api/static/redoc.yaml` или по адресу:
[redoc](http://http://51.250.72.161/redoc/)

## Как запустить проект

Для запуска приложения необходимо создать файл .env в корневой папке проекта
и заполнить его переменными:

```bash
cp .env.example .env
```

Собрать образы Docker:

```docker
sudo docker build -t yamdb .
```

Запустить контейнеры:

```docker
sudo docker-compose up
```

Выполнить миграции:

```docker
sudo docker-compose exec web python manage.py migrate
```

Создать суперпользователя (для раздачи прав админам):

```docker
sudo docker-compose exec web python manage.py createsuperuser
```

Выполнить команду для заполнения базы данными:

```docker
docker-compose exec web python manage.py import_csv
```

Создать дамп (резервную копию) базы:

```docker
sudo docker-compose exec web python manage.py dumpdata > fixtures.json
```

## Проект создан

[Katrin Sakharova](https://github.com/KatrinDevelopment/)
[Oleg Kolesov](https://github.com/inkoff)
[Violetta Tsoy](https://github.com/Violetta-tsoy)

Мы знаем, что разработка программного обеспечения может быть довольно сложной
задачей, поэтому мы здесь, чтобы помочь! Если вы столкнулись с проблемами,
которые не удается решить самостоятельно, не беспокойтесь - наша команда готова
прийти на помощь, пишите на jessup@yandex.ru. Кроме того, если вы знаете, как
исправить ошибку в нашем коде, мы всегда рады новым контрибьюторам и открыты
для вашей помощи. Вместе мы можем создать лучший продукт для всех!
