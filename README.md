# DOCKER COMPOSE COMMANDS

`docker-compose build -h`
`docker-compose build`
`docker-compose up -d`
`docker-compose ps`
`docker-compose down`

### Crear una aplicacion de Laravel en un contenedor

```
docker run --rm -i -t \
-v $(pwd):/opt \
-w /opt \
--network stydedocker_stydenet \
stydedocker/php \
composer create-project laravel/laravel application
```

### Instalar el paquete predis/predis con composer

```
docker run --rm -i -t \
-v $(pwd)/application:/opt \
-w /opt \
--network stydedocker_stydenet \
stydedocker/php \
composer require predis/predis
```

### Instalar autenticacion de Laravel

```
docker run --rm -i -t \
-v $(pwd)/application:/opt \
-w /opt \
--network stydedocker_stydenet \
stydedocker/php \
php artisan make:auth
```

### Migrar la base de datos

```
docker run --rm -i -t \
-v $(pwd)/application:/opt \
-w /opt \
--network stydedocker_stydenet \
stydedocker/php \
php artisan migrate
```