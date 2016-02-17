# ExpressJS: Static Files

create `public/index.html`.

```js
// to use path, do `npm install path` first
var path = require("path")

// the arg inside `.use()` method is the middleware that we're going to use
app.use(express.static(process.argv[3]||path.join(__dirname, 'public')));
```

