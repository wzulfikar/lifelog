# TDD with Gulp and Laravel Elixir

isntall `gulp` and `laravel-elixir`
```js
// package json
{
  "devDependencies": {
    "gulp": "^3.9.1",
    "laravel-elixir": "^6.0.0-9"
  }
}
```

```js
// gulpfile.js
var elixir = require('laravel-elixir');

elixir(function(mix) {
  mix.phpSpec();
});
```

run `gulp tdd`.