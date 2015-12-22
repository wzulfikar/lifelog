# Draft/Hi array, do you have this?

- check if an array in php has given keys:

```php
function validatePayload($payload, $keys)
{
	// set required keys
	$required_keys = array_flip($keys);

	// check $payload against $required_keys for anmissing key(s)
	$missing			 = array_diff_key($required_keys, $payload )

	if($missing_keys = array_keys($missing))
		throw new Exception('Missing payload: `'.implode(', ', $missing_keys ));
}

```

### Usage

```php
validatePayload($payload,['user','command']);
```