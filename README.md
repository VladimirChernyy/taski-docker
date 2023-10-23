#  Проект «Taski»

## Описание проекта:

Проект Taski - это ежедневник который позволяет пользователям записывать свои дела на день. 

![2023-10-23_10-35_1](https://github.com/VladimirChernyy/tileshop/assets/116533449/16fbb734-bbd7-468d-9c84-0fb6a34caa3f)
![2023-10-23_10-35](https://github.com/VladimirChernyy/tileshop/assets/116533449/925124bf-0a6f-4a68-80b8-14b5346bcc8d)
![2023-10-23_10-34](https://github.com/VladimirChernyy/tileshop/assets/116533449/21193bd5-64de-4477-9a8e-b869e6c081c6)

## В проекте были использованы технологии:
Django REST
Python 3.9
Gunicorn
Nginx
PostgreSQL
Docker

## Попробовать демо-версию:
* [Taski](https://ya-taski.ddns.net/)
---

## Как запустить проект:



 Настраиваем Docker
``` 
sudo apt update
sudo apt install curl
curl -fSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
sudo apt-get install docker-compose-plugin;
``` 
Клонируйте с GitHub проект и перейдите в директорию проекта.
``` 
git@github.com:VladimirChernyy/taski-docker.git

cd taski-docker
``` 

Создаем файл .env, в котором нужно указать данные

``` 
sudo nano .env
```
Добавьте в файл .env код  

```
POSTGRES_DB=<Желаемое_имя_базы_данных>
POSTGRES_USER=<Желаемое_имя_пользователя_базы_данных>
POSTGRES_PASSWORD=<Желаемый_пароль_пользователя_базы_данных>
DB_HOST=db
DB_PORT=5432
```

Соберите и запустите контейнеры в фоновом режиме
```
sudo docker compose -f docker-compose.yml up -d
```
Примените миграции
```
sudo docker compose -f docker-compose.yml exec backend python manage.py migrate
```
Соберите статику
```
sudo docker compose -f docker-compose.yml exec backend python manage.py collectstatic
```

Создайте суперпользователся
```
sudo docker compose -f docker-compose.yml exec backend python manage.py createsuperuser
```

![main.yml](https://github.com/VladimirChernyy/foodgram-project-react/actions/workflows/main.yml/badge.svg)

## Над проектом работал:
[Vladimir Chernyy](https://github.com/VladimirChernyy)
