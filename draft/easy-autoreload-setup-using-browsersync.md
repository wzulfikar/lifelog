- download npm
- install gulp and save as dev dep
`npm i gulp --save-dev`
- install browsersync and save as dev dep
`npm i browser-sync --save-dev`

- create gulpfile

```js
// gulpfile.js
var gulp = require('gulp');
var bs = require('browser-sync').create();

gulp.task('browser-sync', [], function() {
    bs.init({
        server: {
            baseDir: "./"
        }
    });
});

gulp.task('watch', ['browser-sync'], function () {
    // watch for changes in html 
    // files and trigger browser reload.
    gulp.watch("*.html").on('change', bs.reload);
});
```
- run `gulp watch`
