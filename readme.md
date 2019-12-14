<p align="center"><img src="https://laravel.com/assets/img/components/logo-laravel.svg"></p>


## My sample dockerized Laravel project

## Enviroment 
* docker : Docker version 17.06.0-ce, build 02c1d87
* docker-compose : docker-compose version 1.15.0, build e12f3b9
* docker-machine : docker-machine version 0.12.1, build c8b17e8

## Run project
1. Compose install :
```
docker run --rm -v $(pwd):/app composer/composer install
```

2. Run docker container with specified service in docker-compose.yml
```
docker-compose up
```

3. Configure enviroment for laravel :
* Enviroment file :
`cp .env.example .env`

* Generate key and optimize commands :
```
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan cache:clear
```

* Migrate database
`docker-compose exec app php artisan migrate --seed`

4. Laravel should work by access http://0.0.0.0:8080
