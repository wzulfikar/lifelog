# Laravel & Datepicker

- user may send date with format `Y-m-d` or `l, d F Y`
  - Sample of `Y-m-d` format : 2017-01-20
  - Sample of `l, d F Y` format : Friday, 20 January 2017

## Steps
- Create BaseModel class and make the models extend from BaseModel instead of Eloquent model
- In BaseModel, create this methods:

```php
public function parseDate($string)
{
  $this->parseTimestamp($string, $asDate = true);
}
```

```php
public function parseTimestamp($string, $asDate = false)
{
  $timestamp      = null;
  $allowedFormats = ['Y-m-d H:i:s', 'Y-m-d', 'l, d F Y'];

  foreach ($allowedFormats as $format) {
    $timestamp = DateTime::createFromFormat($format, $string);
    if($timestamp) break;
  }

  if(!$timestamp){
    abort(500, 'Invalid timestamp format: '.$string);
  }

  return $timestamp->format( $asDate ? 'Y-m-d H' : 'Y-m-d H:i:s' );
}
```

- You can use parseDate or parseTimestamp from anywhere within model that extends BaseModel
- `parseDate` will always return date (`Y-m-d`)
- `parseTimestamp` will always return timestamp (`Y-m-d H:i:s`) 