# CSV Walker.js

```js
var fs   = require('fs');
var path = require('path');

var dir = process.argv[2];

var csvWalker = functiovar fs   = require('fs');
var path = require('path');

var dir = process.argv[2];

var csvWalker = function (currentPath) {
  console.log('Current path: '+currentPath);
  
  var csvFiles = [];
  var files = fs.readdirSync(currentPath);

  for (var i in files) {
    var currentFile = currentPath + '/' + files[i];
    var stats = fs.statSync(currentFile);
    if (stats.isFile()) {
      var isCsv = path.basename(currentFile).split('.')[1] == 'csv';

      if(isCsv){
        csvFiles.push(currentFile);
      }

      console.log(currentFile+' '+(isCsv ? 'is csv':'not csv'));
    }
    else if (stats.isDirectory()) {
      csvWalker(currentFile);
    }
  }
  return csvFiles;
};

if(dir) csvWalker(dir);

module.exports = csvWalker;
```