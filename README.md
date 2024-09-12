# Docker setup for Laravel projects

### Steps

Clone the setup-docker-laravel repository
```sh
git clone https://github.com/igorcfernandes/setup-docker-laravel.git
```

Clone laravel repository
```sh
git clone https://github.com/laravel/laravel.git laravel-app
```

Copy the docker-compose.yml and Dockerfile files and the docker/ directory inside your project
```sh
cp -rf setup-docker-laravel/* laravel-app/
```

Go to your project folder
```sh
cd laravel-app/
```

Create the .env file
```sh
cp .env.example .env
```

Update the environment variables in .env file
```dosini
APP_URL=http://localhost:8000

DB_CONNECTION=mysql
DB_HOST=db
DB_DATABASE=laravel
DB_USERNAME=username
DB_PASSWORD=password

CACHE_DRIVER=redis
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis

REDIS_HOST=redis
```

Start all the services
```sh
docker-compose up -d
```

Run the following shell command inside the app container to interact with the running container
```sh
docker-compose exec app bash
```

Install the project dependencies
```sh
composer install
```

Generate the laravel project key
```sh
php artisan key:generate
```

Access the project
[http://localhost:8000](http://localhost:8000)