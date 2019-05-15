# Kudo board

## Deployment

* Build the container and run all the needed services
```sh
docker-compose up -d
```

Then we need to copy our environment variables
```sh
cp .env.example .env
```

Install the dependencies, generate encryption key and run migrations
```sh
docker-compose run app composer install
docker-compose run app php artisan key:generate
docker-compose run app php artisan migrate --seed
```

For asset building we recommend using local yarn installation.

Then, go to localhost:8080