Magento 2 Docker Image
=================================

To start, use

    docker-compose up -d

If `SAMBA_START=1` is set as an environment variable when the
container is started, a Samba server is launched to give remote
access to the files in the container. Just remember that Samba
can slow things down.

Current build: 
* PHP 7.0.9
* MariaDB 10.1 


