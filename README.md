# Laravel Swagger Schemas Api

## Installation

Install the package via composer:

```shell script
composer require arpanext/laravel-swagger-schemas-api
```

Publish the config file with:

```shell script
php artisan vendor:publish --provider=Arpanext\\Swagger\\Schemas\\Api\\App\\Providers\\AppServiceProvider --tag="swagger-schemas-api"
```

Update the coofig file in config/vendor/arpanext/swagger/schemas/api/schemas.php:

```php
return [
    'default' => [
        'path' => 'app/Http/Controllers/Api',
    ],
];
```

```shell
php artisan route:list --compact
```

```shell
+----------+-----------------------------------+------------------------------------------------------------------------------------------------------+
| Method   | URI                               | Action                                                                                               |
+----------+-----------------------------------+------------------------------------------------------------------------------------------------------+
| GET|HEAD | api/v1/swagger/schemas            | Arpanext\Swagger\Schemas\Api\App\Http\Controllers\Api\Swagger\Schemas\IndexController                |
| GET|HEAD | api/v1/swagger/schemas/{key}.json | Arpanext\Swagger\Schemas\Api\App\Http\Controllers\Api\Swagger\Schemas\ShowController                 |
+----------+-----------------------------------+------------------------------------------------------------------------------------------------------+

```

```shell
curl http://127.0.0.1:8000/api/v1/swagger/schemas
```

```shell
curl http://127.0.0.1:8000/api/v1/swagger/schemas/default.json
```

## Testing

```shell
vendor/bin/phpunit vendor/arpanext/laravel-swagger-schemas-api --configuration=vendor/arpanext/laravel-swagger-schemas-api/phpunit.xml --do-not-cache-result --coverage-text --coverage-html=coverage/html/laravel-swagger-schemas-api
```
