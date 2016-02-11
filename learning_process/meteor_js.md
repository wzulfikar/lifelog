# Meteor JS

*[https://www.meteor.com]()*

>Meteor parses all of the HTML files in your app folder and identifies three top-level tags: `<head>`, `<body>`, and `<template>`.

>The special thing about collections in Meteor is that they can be accessed from both the server and the client.

```javascript
// Creating collection in Meteor
var MyCollection = new Mongo.Collection("my-collection");
```
On the server, above code will set up a MongoDB collection called my-collection; on the client, it creates a cache connected to the server collection

http://www.meteorpedia.com/read/REST_API

https://www.discovermeteor.com/blog/scaling-meteor-the-challenges-of-realtime-apps/

https://projectricochet.com/blog/meteor-js-performance#.Vrj0P7NdXCJ

https://trello.com/b/hjBDflxp/meteor-roadmap

http://blog.differential.com/the-not-so-real-problems-of-meteorjs/

https://www.discovermeteor.com/blog/meteor-methods-client-side-operations/

https://forums.meteor.com/t/webpack-compiler-inside-meteor-es6-modules-hot-reload-and-code-splitting/11264

https://medium.com/@omriklinger/how-to-send-1000-updates-sec-per-client-using-meteor-and-stay-alive-88eba7588c36#.odu33o5vd

## Telescope JS
> Telescope is an open-source, real-time social news site built with Meteor.

http://www.telescopeapp.org
https://github.com/TelescopeJS/Telescope