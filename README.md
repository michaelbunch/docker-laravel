# Docker Laravel

Docker containers for starting a Laravel project.

## Requirements

You will need to have Docker running in some capacity.

* Locally: Docker for Mac, Linux, or Windows
* VM: Vagrant, VirtualBox, or another virtual machine

## How To Use

NOTE: These instructions assume you familiar with Docker.

Copy and past the `containers` folder and `docker-compose.yml` file to the root of you Laravel (or PHP) project.

From the environment that has Docker installed and running, issue the following command from your project root.

```
docker-compose up -d
```

Once the startup process is complete, go to `http://localhost:8080`. If you are running Docker in a VM, you may
need to use the IP address of the VM instead of `localhost`.

There are is also an example `.env` file to show how PHP can access the containers for database, queues, and sessions.

## Containers

Most container names are generic to allow their images to be swapped for similar technologies easier. For example, the
web container currently uses Nginx but this could be swapped with Apache or Caddy without needing to change other settings.

### Web

Nginx container that runs handles web requests. It routes requests that require PHP to the app container for processing.

### App

PHP-FPM container for processing PHP files.

### DB

Database container that uses MariaDB. This can be switched to other database containers like MySQL, Postgres, etc.

### Redis

Redis container.
