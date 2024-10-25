install and self-trust mkcert

cd docker/certs && mkcert laravel.local

cd ../

docker compose up &

docker exec -it php bash

cd laravel && composer install

cp .env.example .env

https://laravel.local
