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
  // try with possible format
  $date = DateTime::createFromFormat('Y-m-d', $stringDate) 
        ?: DateTime::createFromFormat('Y-m-d H:i:s', $stringDate)
        ?: DateTime::createFromFormat('l, d F Y', $stringDate);

  if(!$date){
    abort(500, 'Invalid date format: '.$value);
  }

  return $date->format('Y-m-d');
}
```

```php
public function parseTimestamp($stringTime)
{
  // try with possible format
  $timestamp = DateTime::createFromFormat('Y-m-d H:i:s', $stringTime) 
             ?: DateTime::createFromFormat('Y-m-d', $stringTime)
             ?: DateTime::createFromFormat('l, d F Y', $stringTime);

  if(!$timestamp){
    abort(500, 'Invalid timestamp format: '.$stringTime);
  }

  return $timestamp->format('Y-m-d H:i:s');
}
```