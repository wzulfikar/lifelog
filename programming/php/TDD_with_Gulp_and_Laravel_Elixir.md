# TDD with Gulp and Laravel Elixir

install `gulp` and `laravel-elixir`
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

elixir.config.appPath = 'src';

elixir(function(mix) {
  mix.phpSpec();
});
```

above example uses `phpspec`. so, install `phpspec` via composer: `composer require phpspec/phpspec`.

run `gulp tdd`.

> the `tdd` task is defined by `laravel-elixir`.

using `phpspec`, you can start defining ur spec with something this: `phpspec describe UserRegistration`

run the spec using `phpspec run` and it will create `UserRegistration` class if you have not created it.

by default, `phpspec` will store classes in `src` directory but the `gulp tdd` task will watch `Elixir.config.appPath + '/**/*.php', 'tdd'`. since the default `appPath` is `app`, we need to change it to `src` so the `tdd` will be triggered if anything inside `src` changed. to change value of elixir `appPath` to `src`, we used `elixir.config.appPath = 'src';`.

if have problem with phpspec keep asking to create class even it exists, check this: https://github.com/phpspec/phpspec/issues/585

> some people used `phpspec` specifically for unit test.
