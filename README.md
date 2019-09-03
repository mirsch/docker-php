# mirsch/php

this docker image is based on https://hub.docker.com/_/php
It contains PHP 7.3 FPM and CLI as well as some common php extensions like bcmath, ldap, gd, pdo_mysql.
Furthermore composer and phpunit are pre installed and xdebug is active.
It runs as an unprivileged user "dev" (password: dev)

Usage example for composer, php-cli, bash and so on:
```bash
docker run -it --rm mirsch/php php --version
docker run -it --rm mirsch/php composer --version
docker run -it --rm mirsch/php phpunit --version
docker run -it --rm mirsch/php bash
```

if you use PHP-FPM mount your workdir to /var/www.

## Example running PHP internal Browser
Here is how to run [GRAV](https://getgrav.org/) as an example for the internal server:\
download and unzip GRAV.  
In the unpacked folder use:
```bash
docker run --rm -it -v ${PWD}:/var/www mirsch/php composer install
docker run --rm -it -v ${PWD}:/var/www -p 8000:8000 mirsch/php php -S 0.0.0.0:8000 system/router.php
```
you can access your site at http://localhost:8000


## Example PHP-FPM and Nginx
... coming soon ...
