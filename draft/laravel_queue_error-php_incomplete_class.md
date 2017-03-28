# Laravel Queue Error: PHP Incomplete Class

this error happens when there’s multiple laravel instances with `QUEUE_DRIVER` set to redis, connecting to same redis server, with same default queue name. 

This is the error log:

```php
No handler registered for command __PHP_Incomplete_Class File base_path/bootstrap/cache/compiled.php at line 9561.
 
#1 base_path/bootstrap/cache/compiled.php(9537): Illuminate\Bus\Dispatcher->getHandlerClass(Object(PHPIncompleteClass))
#2 base_path/bootstrap/cache/compiled.php(9493): Illuminate\Bus\Dispatcher->resolveHandler(Object(PHPIncompleteClass))
#3 internal function: Illuminate\Bus\Dispatcher->Illuminate\Bus\{closure}(Object(PHPIncompleteClass))
#4 base_path/bootstrap/cache/compiled.php(9643): calluserfunc(Object(Closure), Object(PHPIncompleteClass))
#5 internal function: Illuminate\Pipeline\Pipeline->Illuminate\Pipeline\{closure}(Object(PHPIncompleteClass))
#6 base_path/bootstrap/cache/compiled.php(9625): calluserfunc(Object(Closure), Object(PHPIncompleteClass))
#7 base_path/bootstrap/cache/compiled.php(9498): Illuminate\Pipeline\Pipeline->then(Object(Closure))
#8 base_path/vendor/laravel/framework/src/Illuminate/Queue/CallQueuedHandler.php(43): Illuminate\Bus\Dispatcher->dispatchNow(Object(PHPIncompleteClass), Object(Closure))
#9 base_path/vendor/laravel/framework/src/Illuminate/Queue/Jobs/Job.php(129): Illuminate\Queue\CallQueuedHandler->call(Object(Illuminate\Queue\Jobs\RedisJob), Array)
#10 base_path/vendor/laravel/framework/src/Illuminate/Queue/Jobs/RedisJob.php(50): Illuminate\Queue\Jobs\Job->resolveAndFire(Array)
#11 base_path/vendor/laravel/framework/src/Illuminate/Queue/Worker.php(208): Illuminate\Queue\Jobs\RedisJob->fire()
```

for this situation, the solution that I know is changing the redis server, or changing the default name. 

for changing the default queue name, we can modify some code inside `config/queue.php` to make it fetch default queue name from our `.env` file. something like:

```php
// config/queue.php
'redis'      => [
  'driver'     => 'redis',
  'connection' => 'default',
  // 'queue'      => 'default',  ← original code
  'queue'      => env('REDIS_DEFAULT_QUEUE', 'default'), // ← workaround
  'expire'     => 60,
],
```
