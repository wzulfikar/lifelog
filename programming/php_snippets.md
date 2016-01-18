# Trim whatever inside array

```php
/**
 * trim whatever inside array
 */

// create array of strings
$untrimmed = [' one  ', 'two ', ' three'];

// trim whatever inside $sample_array using `array_map`
$trimmed      = array_map('trim', $untrimmed);

// see the difference
var_dump($untrimmed);
var_dump($trimmed);
```
```php
// Output:
>>> var_dump($untrimmed);
array(3) {
  [0] =>
  string(6) " one  "
  [1] =>
  string(4) "two "
  [2] =>
  string(6) " three"
}
>>> var_dump($trimmed);
array(3) {
  [0] =>
  string(3) "one"
  [1] =>
  string(3) "two"
  [2] =>
  string(5) "three"
}
```