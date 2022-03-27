## Document Server and Nextcloud Docker installation

Готовый написанный Docker-compose.yml 
Устанавливаются следующие контейнеры: 
1) Nextcloud 
2) OnlyOffice
3) Nginx
4) PostgreSQL

Document Server (distributed as ONLYOFFICE Docs starting from v.6.0) and Nextcloud Docker installation will install the preconfigured version of [ONLYOFFICE Document Server][2] connected to Nextcloud to your server running them in Docker containers.


## Requirements

* Последнюю версию Docker (можно скачать здесь: [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/))
* Docker compose (можно скачать здесь: [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/))


## Installation

1. Что бы подтянуть файлы на нашу станцию введите следующие команды:

    ```
    git clone https://github.com/Kaisarhan/docker-compose-nextcloud
    ```

2. Run Docker Compose:
    Прежде чем запустить команду нужно войти в папку docker-compose-nextcloud
    **Please note**: Затустить от имени **root** или **sudo docker-compose up -d**.

    ```
    docker-compose up -d
    ```

    **Please note**: Вам может потребоваться подождать пару минут, когда все контейнеры будут запущены и будут работать после указанной выше команды.

3. Теперь запустите браузер и введите адрес веб-сервера. Откроется веб-страница мастера Nextcloud здесь же нужно указать вашу БД PostgreSQL. Введите все необходимые данные для завершения работы мастера.

Ваш сервер: db

Ваша база данных: nextcloud

Имя пользователя db: postgres

Пароль нужно будет указать в Docker-compose.yml



Пароль бд указывается в docker-compose.yml **POSTGRES_PASSWORD=ваш пароль**


4. Перейдите в папку проекта и запустите скрипт `set_configuration.sh`:

    **Please note**: действие должно производиться с правами **root**.

    ```
    bash set_configuration.sh
    ```

Теперь вы можете войти в Nextcloud и создать новый документ. Он будет открыт на Сервере документов ONLYOFFICE.


## Все команды каторый возможно помогут вам.

**Docker-compose**

* Команда для входа в контейнер и выполнять команды из контейнера:
    ```
   docker exec -it container_name bash
    ```
    
**NextCloud:**

* Переход в режим обслуживание. Если нужно будет выключить режим обслуживание поменяйте значение на --off

    ```
    docker exec -u www-data container_name php occ maintenance:mode --on
    ```
    
**Postgres:**

* BackUp database Postgres
    
    ```
    docker exec container_name pg_dump -c -U postgres_user db_name > new_backup_name`date +"%Y%m%d"`.dump
    ```
    или
    ```
    docker exec db pg_dump -U postgres -f nextcloud > nextcloud-sqlbkp_`date +"%Y%m%d"`.bak
    ```

## Project Information

Official website: [https://www.onlyoffice.com/](https://www.onlyoffice.com/?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC)

Code repository: [https://github.com/ONLYOFFICE/docker-onlyoffice-nextcloud](https://github.com/ONLYOFFICE/docker-onlyoffice-nextcloud "https://github.com/ONLYOFFICE/docker-onlyoffice-nextcloud")


## User Feedback and Support

If you have any problems with or questions about [ONLYOFFICE Document Server][2], please visit our official forum to find answers to your questions: [forum.onlyoffice.com][1] or you can ask and answer ONLYOFFICE development questions on [Stack Overflow][3].

[1]: https://forum.onlyoffice.com
[2]: https://github.com/ONLYOFFICE/DocumentServer
[3]: http://stackoverflow.com/questions/tagged/onlyoffice
