# Using Cent to Represent Currency

```php
function denominate($int){
    return number($int/100, 2);
}
```

References: 
- http://stackoverflow.com/questions/3730019/why-not-use-double-or-float-to-represent-currency