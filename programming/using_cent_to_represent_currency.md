# Using Cent to Represent Currency

Double, float, they shouldn't be used for anything that requires accuracy.

>There are some numbers which cannot be represented accurately using float point representation. Consider, for example, pi. How would you represent a number which has infinite digits, within a finite storage?   http://stackoverflow.com/a/960078

```php
function denominate($int){
    return number_format($int/100, 2);
}
```

References: 
- http://docs.oracle.com/cd/E19957-01/806-3568/ncg_goldberg.html
- http://stackoverflow.com/questions/3730019/why-not-use-double-or-float-to-represent-currency
- http://stackoverflow.com/questions/960072/rounding-errors