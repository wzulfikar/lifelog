# Artisan console: managing exit code

- Create constant in artisan console class, e.g:

```php
public static $EXIT_CODE = [
    'FAILED'=>-1,
    'USER_NOT_FOUND'=>0,
    'SUCCESS'=>1
];
```