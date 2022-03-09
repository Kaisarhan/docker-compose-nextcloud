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


## ONLYOFFICE Docs editions

Here we offer you to deploy Nextcloud with preconfigured free version of ONLYOFFICE Docs (Document Server). Note that there're commercial versions of it. 

**ONLYOFFICE Docs:**

* Community Edition (`onlyoffice-documentserver` package)

* Enterprise Edition (`onlyoffice-documentserver-ee` package)

The table below will help you make the right choice.

| Pricing and licensing | Community Edition | Enterprise Edition |
| ------------- | ------------- | ------------- |
| | [Get it now](https://www.onlyoffice.com/download-docs.aspx?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC#docs-community)  | [Start Free Trial](https://www.onlyoffice.com/download-docs.aspx?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC#docs-enterprise)  |
| Cost  | FREE  | [Go to the pricing page](https://www.onlyoffice.com/docs-enterprise-prices.aspx?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC)  |
| Simultaneous connections | up to 20 maximum  | As in chosen pricing plan |
| Number of users | up to 20 recommended | As in chosen pricing plan |
| License | GNU AGPL v.3 | Proprietary |
| **Support** | **Community Edition** | **Enterprise Edition** | 
| Documentation | [Help Center](https://helpcenter.onlyoffice.com/installation/docs-community-index.aspx) | [Help Center](https://helpcenter.onlyoffice.com/installation/docs-enterprise-index.aspx) |
| Standard support | [GitHub](https://github.com/ONLYOFFICE/DocumentServer/issues) or paid | One year support included |
| Premium support | [Buy Now](https://www.onlyoffice.com/support.aspx?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC) | [Buy Now](https://www.onlyoffice.com/support.aspx?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC) |
| **Services** | **Community Edition** | **Enterprise Edition** |
| Conversion Service                | + | + |
| Document Builder Service          | + | + |
| **Interface** | **Community Edition** | **Enterprise Edition** |
| Tabbed interface                       | + | + | 
| Dark theme                             | + | + |
| 150% scaling                           | + | + |
| White label                            | - | - |
| Integrated test example (node.js)*     | - | + |
| Mobile web editors                     | - | + |
| Access to pro features via desktop     | - | + |
| **Plugins & Macros** | **Community Edition** | **Enterprise Edition** |
| Plugins                           | + | + |
| Macros                            | + | + |
| **Collaborative capabilities** | **Community Edition** | **Enterprise Edition** |
| Two co-editing modes              | + | + |
| Comments                          | + | + |
| Built-in chat                     | + | + |
| Review and tracking changes       | + | + |
| Display modes of tracking changes | + | + |
| Version history                   | + | + |
| **Document Editor features** | **Community Edition** | **Enterprise Edition** |
| Font and paragraph formatting   | + | + |
| Object insertion                | + | + |
| Adding Content control          | - | + | 
| Editing Content control         | + | + | 
| Layout tools                    | + | + |
| Table of contents               | + | + |
| Navigation panel                | + | + |
| Mail Merge                      | + | + |
| Comparing Documents             | - | +* |
| **Spreadsheet Editor features** | **Community Edition** | **Enterprise Edition** |
| Font and paragraph formatting   | + | + |
| Object insertion                | + | + |
| Functions, formulas, equations  | + | + |
| Table templates                 | + | + |
| Pivot tables                    | + | + |
| Data validation                 | + | + |
| Conditional formatting  for viewing | +** | +** |
| Sheet Views                     | - | + |
| **Presentation Editor features** | **Community Edition** | **Enterprise Edition** |
| Font and paragraph formatting   | + | + |
| Object insertion                | + | + |
| Transitions                     | + | + |
| Presenter mode                  | + | + |
| Notes                           | + | + |
| | [Get it now](https://www.onlyoffice.com/download-docs.aspx?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC#docs-community)  | [Start Free Trial](https://www.onlyoffice.com/download-docs.aspx?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC#docs-enterprise)  |

\*  It's possible to add documents for comparison from your local drive, from URL and from Nextcloud storage.

\** Support for all conditions and gradient. Adding/Editing capabilities are coming soon

## Project Information

Official website: [https://www.onlyoffice.com/](https://www.onlyoffice.com/?utm_source=github&utm_medium=cpc&utm_campaign=GitHubDockerNC)

Code repository: [https://github.com/ONLYOFFICE/docker-onlyoffice-nextcloud](https://github.com/ONLYOFFICE/docker-onlyoffice-nextcloud "https://github.com/ONLYOFFICE/docker-onlyoffice-nextcloud")


## User Feedback and Support

If you have any problems with or questions about [ONLYOFFICE Document Server][2], please visit our official forum to find answers to your questions: [forum.onlyoffice.com][1] or you can ask and answer ONLYOFFICE development questions on [Stack Overflow][3].

[1]: https://forum.onlyoffice.com
[2]: https://github.com/ONLYOFFICE/DocumentServer
[3]: http://stackoverflow.com/questions/tagged/onlyoffice
