# Objective

This is a project related to a school assignment.
To meet the requirements of the assignment, this project will use Docker to prepare the following environment.

* Jenkins
* Application server and database server
  * PHP
  * MySQL (MariaDB)
* PHP application
  * Application with registration and login functionality (using Laravel)

In addition, CircleCI configuration is included.

# Requirements

- Docker and docker-compose (As the host, Linux environment is recommended)
- Reverse Proxy (e.g., nginx)
  This project does not provide a container port to the outside world.
  You may need to use a reverse proxy such as nginx to see how it works.

# Tips

## How to work

```
docker-compose up -d --build
```

## How to migrate database using Laravel (artisan)

```
docker-compose exec app bash -c 'cd /docroot && php artisan migrate'
```

## How to know initialAdminPassword for Jenkins

```
docker-compose exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

## How to access to inside of containers using bash

```
docker-compose exec app bash -l
docker-compose exec db bash -l
docker-compose exec jenkins bash -l
```

Enjoy!!
