# HTTP Request

PHP functions to handle sending and receiving HTTP requests with CURL.


# Installation
Easy install with composer:
```
composer require hxgf/http-request
```
```php
use HTTPRequest\http;
require __DIR__ . '/vendor/autoload.php';
```


# Usage
## http::request($url, $parameters)
Makes an http request to a given url, sending an array of data, and returns the raw response.
```php
$data = http::request('https://external-api.com/v3/example-response', [
  'method' => 'GET', // optional, POST by default, GET and POST supported currently
  'format' => 'json' // return an expected JSON response as a PHP array
  data => [
    'user_id' => 581146,
    'api_key' => '696719xvckvzxspigh24y1e-b'
  ]
]);
```

## http::get($url, $parameters)
Alias to `http::request` using the `GET` method.
```php
$data = http::get('https://external-api.com/v3/example-response', [
  data => [
    'user_id' => 581146,
    'api_key' => '696719xvckvzxspigh24y1e-b'
  ]
]);
```

## http::post($url, $parameters)
Alias to `http::request` using the default `POST` method.
```php
$data = http::post('https://external-api.com/v3/example-response', [
  data => [
    'user_id' => 581146,
    'api_key' => '696719xvckvzxspigh24y1e-b'
  ]
]);
```

## http::json($url, $parameters)
Alias to `http::request()` using the `json` format parameter (returns an expected JSON response as a PHP array)
```php
$data = http::json('https://external-api.com/v3/example-response', [
  data => [
    'user_id' => 581146,
    'api_key' => '696719xvckvzxspigh24y1e-b'
  ]
]);
```
