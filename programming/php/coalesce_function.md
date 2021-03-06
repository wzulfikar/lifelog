# Coalesce Function

```php
/**
 * Takes at least 2 arguments: truth test & output if the test passed.
 * If the args more than 2, the last arg will be the output if truth tests failed,
 * and the before-last arg will be the output if all truth tests passed.
 * 
 * @return mixed
 */
function coalesce(){
	$numArgs = func_num_args();
	if($numArgs < 2)
		throw new \Exception('insufficient args, should be at least 2 instead of 1');

	if( $numArgs < 3)
		return func_get_args()[0] ? func_get_args()[1] : null;

	$args   = func_get_args();
	$output_false = array_pop($args);
	$output_true  = array_pop($args);
	
	foreach ($args as $truth) {
		if(!$truth) return $output_false;
	}

	return $output_true;
}
```