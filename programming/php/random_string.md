# Random String
```php
/**
 * generate random str consists of 
 * name of color, 4 digits int and a character.
 *
 * eg. bronze1459!, silver9627?, gold7062$, lemon4824!
 * 
 * @return string
 */
function random_str()
{
  $colors = [ 
    'blue', 'bronze', 'brown', 'cream', 'cyan', 'gold', 'green', 'lemon', 'lime', 'magenta', 'maroon', 'orange', 'pink', 'purple', 'rose', 'rust', 'silver', 'violet', 'white' 
  ];

  $chars = ['!', '?', '$', '*'];

  $color = $colors[random_int(0, count($colors) - 1)];
  $digit = random_int(1000, 9999);
  $char  = $chars[random_int(0, count($chars) - 1)];
  
  return $color . $digit . $char;
}
```
