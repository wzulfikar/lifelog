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
Say, we want to validate whether a `$_POST` contains `username` & `password`. Let's do:

```php
validatePayload($_POST, ['username','password']);
```
Using above code, if given `$_POST` (the payload) contains both `username` & `password`, script will carry on the execution. Otherwise, it will throw exception.