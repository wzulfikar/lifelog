# PHP Snippets

```php
/**
 * trim all strings inside array
 */

// create array of strings as sample
$sample_array = [' one  ', false, ' three'];

// trim whatever inside $sample_array using `array_map`
$trimmed      = array_map('trim', $sample_array);

// see the difference
var_dump($sample_array);
var_dump($trimmed);
```