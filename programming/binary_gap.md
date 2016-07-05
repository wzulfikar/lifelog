# Binary Gap

```php
function solution($N) {
    $bin = str_split(decbin($N));
    $seq = [];
    $ctr = 0;

    foreach($bin as $val){
        
        if(!$val){
            $ctr++;
            continue;
        }
        $seq[] = $ctr;
        $ctr   = 0;
    }
    
    return max($seq);
}
```

