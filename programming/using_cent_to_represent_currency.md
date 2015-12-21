# Using Cent to Represent Currency

Double, float, they shouldn't be used for anything that requires accuracy.

```php
function denominate($int){
    return number($int/100, 2);
}
```

References: 
- http://docs.oracle.com/cd/E19957-01/806-3568/ncg_goldberg.html
- http://stackoverflow.com/questions/3730019/why-not-use-double-or-float-to-represent-currency
- http://stackoverflow.com/questions/960072/rounding-errors