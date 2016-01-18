# PHP Snippets

```php
/**
 * trim items inside array
 */

// create array of strings
$untrimmed = [' one  ', 'two ', ' three'];

// trim whatever inside $sample_array using `array_map`
$trimmed      = array_map('trim', $untrimmed);

// see the difference
var_dump($untrimmed);
var_dump($trimmed);
```