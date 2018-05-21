<p align="center"> <img src="https://cdn.rawgit.com/MrGKanev/locally/master/img/server.svg" height="125"></p>

# Locally
## :construction: This repo is in early stage! :construction:
So yes it is another Docker based system. I used something else before but it was too mainstream so i build my own. 

## Getting Started
If you feel I am missing interesting things, put it on the [issues](https://github.com/mrgkanev/locally/issues) and I'll definitely try it out.


### Prerequisites

- An OS
- Docker
- Git


### Running

Start:

```bash
$ docker-compose up -d
```

Stop:

```bash
$ docker-compose stop
```



End with an example of getting some data out of the system or using it for a little demo

## Services exposed outside your environment ##

You can access your application via **`localhost`**, if you're running the containers directly, or through **``** when run on a vm. nginx and mailhog both respond to any hostname, in case you want to add your own hostname on your `/etc/hosts` 

Service|Address outside containers
------|---------|-----------
Webserver|[localhost:1800](http://localhost:1800)
Mailhog web interface|[localhost:1801](http://localhost:1801)
MariaDB|**host:** `localhost`; **port:** `1803`

## Hosts within your environment ##

You'll need to configure your application to use any services you enabled:

Service|Hostname|Port number
------|---------|-----------
php-fpm|php-fpm|9000
MariaDB|mariadb|3306 (default)
Redis|redis|6379 (default)
SMTP (Mailhog)|mailhog|1025 (default)

## Deployment

Simply, unzip the file into your project, this will create `docker-compose.yml` on the root of your project.

# Docker compose cheatsheet #

**Note:** you need to cd first to where your docker-compose.yml file lives.

  * Start containers in the background: `docker-compose up -d`
  * Start containers on the foreground: `docker-compose up`. You will see a stream of logs for every container running.
  * Stop containers: `docker-compose stop`
  * Kill containers: `docker-compose kill`
  * View container logs: `docker-compose logs`
  * Execute command inside of container: `docker-compose exec SERVICE_NAME COMMAND` where `COMMAND` is whatever you want to run. Examples:
        * Shell into the PHP container, `docker-compose exec php-fpm bash`
        * Run symfony console, `docker-compose exec php-fpm bin/console`
        * Open a mysql shell, `docker-compose exec mysql mysql -uroot -pqwerty`

## Built With

* [Docker](https://www.docker.com/) - Docker is the world’s leading software containerization platform.
* [Nginx](https://www.nginx.com/) - NGINX accelerates content and application delivery, improves security, facilitates availability and scalability for the busiest web sites on the Internet.
* [MariaDB](https://mariadb.org/) -One of the most popular database servers. Made by the original developers of MySQL. Guaranteed to stay open source.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Docker wiki
