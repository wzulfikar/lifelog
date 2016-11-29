# Using Nunjucks HTML Template Engine with Gulp

- install `nunjucks` for gulp:

  `npm install --save-dev gulp-nunjucks-render`

- create gulpfile.js in root directory of your project:

```js
// gulpfile.js

var gulp = require('gulp'),
    nunjucksRender = require('gulp-nunjucks-render');

// writing up the gulp nunjucks task
gulp.task('nunjucks', function() {
    console.log('Rendering nunjucks files..');
        return gulp.src('src/pages/**/*.+(html)')
        .pipe(nunjucksRender({
            path: ['src/templates/'],
            watch: true,
        }))
        .pipe(gulp.dest('dist'));
});

gulp.task('watch', function() {
    gulp.watch(['src/pages/**/*.+(html)', 'src/templates/**/*.+(html)'], ['nunjucks']);
});

//default task to be run with gulp
gulp.task('default', ['nunjucks']);

```

- render files: `gulp`

- watch files and auto render when something changes: `gulp watch`
