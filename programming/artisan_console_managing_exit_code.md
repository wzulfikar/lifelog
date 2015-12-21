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
Assuming that below code is my `UserLogin` console:
```php
public static $EXIT_CODE = [
    'FAILED'=>-1,
    'USER_NOT_FOUND'=>0,
    'SUCCESS'=>1
];
public function __construct()
{
    parent::__construct();
}
public function handle(){
    // get userId from argument & find the user
    $userId = $this->argument('userId');
	$user = User::find($userId);
    
    // return earlier if no user found
	if(!$user) return self::$EXIT_CODE['USER_NOT_FOUND'];
    
    // login the user
	auth()->loginUsingId($user->id);
    
    // fire event
	event(new UserLoginSucceed);
	
	// give return code for succesful execution
	return self::$EXIT_CODE['SUCCESS'];
};
```

And in `UserController`, I'll do:
```php
$exitCode = Artisan::call('user:login',
                          [
                            'userId'=>'1',
                            'password'=>'pass'
                          ]
                         );
if($this->translateCommandExitCode('UserLogin',$exitCode) == 'FAILED'){
    // do code when exit code is FAILED
}
```