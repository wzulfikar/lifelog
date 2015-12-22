# Hi `payload`, do you have this?
### The Function (PHP)
```php
function validatePayload($payload, $keys)
{
	$required_keys = array_flip($keys);

	// diff $payload against $required_keys
	$missing	   = array_diff_key($required_keys, $payload )

	if($missing_keys = array_keys($missing))
		throw new Exception('Missing key in payload: `'.implode(', ', $missing_keys ));
}

```

### Usage

```php
validatePayload($payload,['user','command']);
```

Above code will validate whether the `$payload` has given key `user` & `command`. So, if we want to validate whether a `$_POST` contains `username` & `password`, we can do this:

```php
validatePayload($_POST, ['username','password']);
```
If the `$_POST` contains both `username` & `password`, script will carry on the execution. Otherwise, it will throw exception.