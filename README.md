# laravel_docker
Docker for Laravel 8.0

## Branches ##
The following maps the plugin version to use depending on your Moodle version.

| Moodle version    | Branch      |
| ----------------- | ----------- |
| Laravel 8         | main        |


## Installing ##
1. Install it using git to clone it into your source:
```
git clone git@github.com:guillogo/laravel_docker.git laravel_docker
```
2. Clone Laravel project
```
git clone git@github.com:laravel/laravel.git src
```
3. Startup the docker environment
```
docker-compose up -d
```
4. Install Laravel dependencies
```
docker-compose exec -T app composer install
```
5. Create a copy of the .env.example file and
```
docker-compose exec -T app cp .env.example .env
```
6. Generate a new encryption key
```
docker-compose exec -T app php artisan key:generate
```
7.Go to http://localhost:8100/

You should see Laravel's default homapage.

### Troubleshooting ###
If you don't get the Laravel's default homepage, please check your console in browser maybe you are getting this exception message:
```
The stream or file \"/var/www/storage/logs/laravel.log\" could not be opened in append mode: Failed to open stream: Permission denied
```
To fix it you can change the folder permission in `/src/storages/`
```
cd src
chmod -R 777 storage/
```

## License ##

2022 Guillermo Gomez <guigomar@gmail.com>

Licensed under the [GNU GPL License](http://www.gnu.org/copyleft/gpl.html).