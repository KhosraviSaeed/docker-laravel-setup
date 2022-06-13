# Docker Laravel Starter
## Installation

 - Extract docker-laravel.zip file 
 - Open a terminal inside the docker-laravel folder and type 
```sh
docker-compose up --build
```
 ## Optional
 - Change containers names and versions in docker-compose.yml file
 - Change ports in .env file
 - Change Php and Composer version in docker/php/Dockerfile file
 - Change phpmyadmin version in the last line of docker-compose.yml
 - To access containers you need to type
```sh
docker exec -it [container_name] bash
```
 - To access sql file type
```sh
docker exec [container_name] /usr/bin/mysqldump -u root --password=password [database_name] > [sql_file_name].sql
```

 ## Common Errors:
 - storage: Permission denied
```sh
sudo chmod o+w ./storage/ -R && php artisan cache:clear
```
 - failed to open stream
```sh
docker exec -it [container_name] bash
composer update
composer dump-autoload
composer install #Run if composer was corrupted 
```

### Making Another Project
> In the case of copying your project to change as another project you need to delete redis, mysql and log files inside docker folder first then, change host ports for nginx, mysql, php, redis and phpmyadmin to get rid of port confliction.
