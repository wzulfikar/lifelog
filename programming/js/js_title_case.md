# JS: Title Case

```
function titleCase(str) {
  return str.toLowerCase().split(' ').map(function(val){
    return val[0].toUpperCase() + val.slice(1);
  }).join(' ');
}

titleCase("I'm a little tea pot");
```

### Test