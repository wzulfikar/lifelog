# Artisan console: managing exit code

- Create constant in artisan console class, e.g:

```php
public static $EXIT_CODE = [
    'FAILED'=>-1,
    'USER_NOT_FOUND'=>0,
    'SUCCESS'=>1
];
```

- And put the code to access that exit code somewhere:

```php
private function translateCommandExitCode($class, $exitCode)
{	
	// retrieve fcqn (fully classified class name)
	$fcqn = '\\App\\Console\\Commands\\' . $class;
    return array_search($exitCode, $fcqn::$EXIT_CODE );
}
```

## Usage
Assuming I'm in `UserController` and already set `translateCommandExitCode` method:
```php
$exitCode = Artisan::call('user:login',
                          [
                            'username'=>'testuser',
                            'password'=>'pass'
                          ]
                         );
$this->translateCommandExitCode('UserLogin',$exitCode) == 'FAILED'
```