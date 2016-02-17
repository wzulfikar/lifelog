# ExpressJS: Hello World!

```js
// require express module (don't forget to `npm install express` first)
var express = require('express');

// create express instance
var app = express();

// make a simple router 
app.get('/home', function(req, res){
	res.end('Hello World!');
});

// initiate listener
app.listen(process.argv[2]);

// run this file using `node path/to/this/file {port}`
```

