# Laravel: Using local package
- in `composer.json` file, add 

```php
"psr-4": {
    "App\\": "app/",
    "Spatie\\Tail\\": "local-packages/laravel-tail/src/"
},
```

think of above snippet as mapping of aliases. `Spatie\\Tail\\` is alias for `local-packages/laravel-tail/src/`. So, when you use class like `Spatie\Tail\MyClass` in your php file, it means you are `MyClass` which is stored inside directory `local-packages/laravel-tail/src/`.

- notice the trailing `\\` in namespace: `App\\`, `Spatie\\Tail\\`
- notice the trailing `/` in path: `app/`, `local-packages/laravel-tail/src/`

if the package is laravel package, don't forget to add its service provider into `config/app.php`.
