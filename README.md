# Magento 2 Docker Image with xDebug, NodeJs, MariaDB


## Usage

If you start a project run the composer create command:
```
composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition <installation directory name>
```
If you are cloning and existing project, clone the project before running the docker-compose up command.

To start, you can just copy the docker-compose.yml file to your project folder and run:

    docker-compose up -d

Depending on your environment you might want to run these commands afterwards:

* composer install in your container
* copy db to your container: docker cp db.sql [container_id]:/magento2/
* log into your container and import db (mysql -u magento -pmagento )
* change the url value in the db (UPDATE core_config_data SET value='http://sitename.docker/' WHERE config_id = 2;)
* chmod a+x bin/magento
* deploy content

## Useful commands:

* docker exec -it [container_id] bash (logs you in the container, apache root folder magento2)
* docker cp folder [container_id]:/magento2/ (copy files from host to container)
* export TERM=xterm (from inside your container if you want to use nano or vim, due to a docker bug: https://github.com/docker/docker/issues/9299)
* bash profile is located at /home/magento/.bashrc

Inside your container if you run php -v you should get:

    PHP 7.0.9 (cli) (built: Jul 29 2016 20:54:37) ( NTS )
    Copyright (c) 1997-2016 The PHP Group
    Zend Engine v3.0.0, Copyright (c) 1998-2016 Zend Technologies
        with Xdebug v2.4.1, Copyright (c) 2002-2016, by Derick Rethans

If `SAMBA_START=1` is set as an environment variable when the
container is started, a Samba server is launched to give remote
access to the files in the container. Just remember that Samba
can slow things down.

## Automatic build (claudiucreanga/magento2-docker) locked at (recommended to use):
* MariaDB 10.1 
* xDebug 2.4.1
* NodeJs 6

## Current manual build (claudiucreanga/magento2): 
* Debian GNU/Linux 8.5
* Apache/2.4.10 (Debian)
* PHP 7.0.9
* MariaDB 10.1 
* xDebug 2.4.1
* NodeJs 6.3.1
* Npm 3.10.3
* Grunt cli 1.2
* Magento2 crons



