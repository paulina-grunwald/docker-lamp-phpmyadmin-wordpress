# Ready-To-Start LAMP stack with Wordpress, PHPMyAdmin in Docker containers

This boilerplate is a ready-to-start customizable LAMP stack (mysql 5.6.34) with Wordpress (latest version with pho 7.0.3), and PHPMyAdmin (latest version) integration.
**Note : for Linux, Windows and MacOS**.

#### Ports

You can have multiple projects using this boilerplate, but without changing ports, only one project can be up at a time, because port 80 is used to expose Apache.

- **APPLICATION_WEB_PORT**: default to `80`.
- **PHP_MY_ADMIN_PORT**: default to `81`.

#### Getting started

In order to get started with blank project you need to take following steps:

1. Clone repo:
   `git clone https://github.com/paulina-grunwald/docker-lamp-phpmyadmin-wordpress.git`
2. Create folders 'www' and 'db' in the project folder.
3. Run following commands in the terminal:

```docker
docker build -t "php703:wordpress" .
docker-compose up
```

5. If you don't have privileges to edit files in folders www and db (happens on Linux) then follow those steps:

- enter wordpress container using command:

```bash
sudo docker exec -it wordpress bash
```

Inside of container execute commands:

```bash
usermod -u 1000 www-data
chown -R www-data:www-data

```

- in your project folder execute command:

```

chmod g+w db

```

### Wordpress

Accessible on `localhost:80` by default.

### PhpMyAdmin

Accessible on `localhost:81` by default. Use `MYSQL_USER` and `MYSQL_PASSWORD` to connect.

#### Useful Docker commands

```docker
# see all running containers
docker ps

# start containers
docker-compose up

# stop all containers
docker-compose down

# restart all containers
docker-compose restart

# enter inside of the container
docker exec -it <container name> /bin/bash



```
