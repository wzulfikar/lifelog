# Auto Reloading The Browser: CodeKit vs BrowserSync.

- I tried codekit, it's awesome tools. can handle a lot of projects including my laravel.
- BrowserSync has its own UI page to customize the setting like scroll-sync, etc. and if you're using Laravel, it supports for BrowserSync out of the box. Awesome!
- for my Laravel project, using codekit feels slower in my machine (MacbookAir 2011, Core i5, 4GB RAM) compared to using BrowserSync (via Laravel Elixir).

## Using CodeKit
- open codekit
- add project
- if using php, add external server
- click preview
- do ur code, any change will reflect automatically

## Using BrowserSync (via Laravel Elixir)
- install browsersync: `npm i laravel-elixir-browsersync-official --save-dev`
- add `browserSync` method in gulpfile
```js
elixir(function(mix) {
    mix.browserSync({
      proxy: 'localhost:8000' // location of your app
    });
});
```
- run the server (for me its laravel): `php artisan serve`
- run browsersync: `gulp watch`

the `gulp watch` will trigger `browserSync` task which in turn opens `localhost:3000` in your browser.