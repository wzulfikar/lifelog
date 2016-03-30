# Laravel & Datepicker

- user may send date with format `Y-m-d` or `l, d F Y`
  - Sample of `Y-m-d` format : 2017-01-20
  - Sample of `l, d F Y` format : Friday, 20 January 2017

## Steps
- Create BaseModel class and make the models extend from BaseModel instead of Eloquent model
- In BaseModel, create this methods:

```php
public function parseDate($stringDate)
{
  $date           = null;
  $allowedFormats = ['Y-m-d', 'Y-m-d H:i:s', 'l, d F Y'];

  foreach ($allowedFormats as $format) {
    $date = DateTime::createFromFormat($format, $stringDate);
    if($date) break;
  }

  if(!$date){
    abort(500, 'Invalid date format: '.$value);
  }

  return $date->format('Y-m-d');
}

```

```php
public function parseTimestamp($stringTime)
{
  $timestamp      = null;
  $allowedFormats = ['Y-m-d H:i:s', 'Y-m-d', 'l, d F Y'];

  foreach ($allowedFormats as $format) {
    $timestamp = DateTime::createFromFormat($format, $stringTime);
    if($timestamp) break;
  }

  if(!$timestamp){
    abort(500, 'Invalid timestamp format: '.$stringTime);
  }

  return $timestamp->format('Y-m-d H:i:s');
}
```

- You can use parseDate or parseTimestamp from anywhere within model that extends BaseModel
- `parseDate` will always return date (`Y-m-d`)
- `parseTimestamp` will always return timestamp (`Y-m-d H:i:s`) 