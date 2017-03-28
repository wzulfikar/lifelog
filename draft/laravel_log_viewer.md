# Laravel Log Viewer

### Installation
Install this package using composer: `composer require rap2hpoutre\laravellogviewer`. Follow next installation step of the package in their github: https://github.com/rap2hpoutre/laravellogviewer

After finishing the installation of above package, add this code in your route file and visit `/app-logs` in your browser.

```php
Route::get('app-logs', [
    'uses' => '\Rap2hpoutre\LaravelLogViewer\LogViewerController@index'
]);
```

## Optional

Adding middleware to add security layer before accessing app logs. 

1. Create a middleware which `handle` method contains this code:

```php
// middleware
public function handle($request, Closure $next)
{
  	$envs = [
  	    'production'
  	];

  	if(in_array(app()->environment(), $envs)) {
  		$user = config('app-logs.user');
  		$password = config('app-logs.password');

  	    if($request->getUser() != $user && $request->getPassword() != $password) {
  	        $headers = ['WWW-Authenticate' => 'Basic'];
  	        return response('Unauthorized', 401, $headers);
  	    }
  	}

  	return $next($request);
}
```

2. Create config file to store user and password for accessing app logs
```php
// config/app-logs.php
return [
	'user' => env('APP_LOGS_USER'),
	'password' => env('APP_LOGS_PASSWORD'),
];
```
