# NodeJS

     var fs = require('fs')  
       
     var contents = fs.readFileSync(process.argv[2])  
     var lines = contents.toString().split('\n').length - 1  
     console.log(lines)  
       
     // note you can avoid the .toString() by passing 'utf8' as the  
     // second argument to readFileSync, then you'll get a String!  
     //  
     // fs.readFileSync(process.argv[2], 'utf8').split('\n').length - 1  

`git clone https://github.com/FreeCodeCamp/fcc-expressworks.git && chmod 744 fcc-expressworks/setup.sh && fcc-expressworks/setup.sh && source ~/.profile` -> `expresswork`

`npm install learnyoumongo -g`

>Whenever you run a command that includes mongod on c9.io, be sure to also use the --nojournal flag, like this: mongod --nojournal.

https://github.com/evanlucas/learnyoumongo
