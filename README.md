### Создание проекта

создаем папку проекта
клонируем туда репу.

```
git clone https://github.com/Grin9l/slamdock8
```

удаляем папку .git из папки docker,
git будет только в папке с проектом

```
cd docker && rm -rf .git
```

### Выполните настройку окружения

Скопируйте файл `.env_template` в `.env`
```
cp -f .env_template .env
```
в .env изменяем COMPOSE_PROJECT_NAME = на имя проекта на латинице.
По умолчанию используется nginx, php8.1, mysql. Настройки можно изменить в файле ```.env```. Также можно задать путь к каталогу с сайтом и параметры базы данных MySQL.

```
PHP_VERSION=php81          # Версия php
WEB_SERVER_TYPE=nginx      # Веб-сервер nginx/apache
DB_SERVER_TYPE=mysql       # Сервер базы данных mysql/percona
MYSQL_DATABASE=bitrix      # Имя базы данных
MYSQL_USER=bitrix          # Пользователь базы данных
MYSQL_PASSWORD=123         # Пароль для доступа к базе данных
MYSQL_ROOT_PASSWORD=123    # Пароль для пользователя root от базы данных
INTERFACE=0.0.0.0          # На данный интерфейс будут проксироваться порты
SITE_PATH=../public        # Путь к директории Вашего сайта
```

### Запуск
внутри папки docker выполняем
```
docker-compose up -d
```
### Остановка
```
docker-compose down
