# Webpack Baby Steps

https://webpack.github.io/docs/tutorials/getting-started/

https://medium.com/@dtothefp/why-can-t-anyone-write-a-simple-webpack-tutorial-d0b075db35ed#.4yc0vsdri

webpack will analyze your entry file for dependencies to other files. These files (called modules) are included in your bundle.js too. webpack will give each module a unique id and save all modules accessible by id in the bundle.js file. Only the entry module is executed on startup. A small runtime provides the require function and executes the dependencies when required.

https://webpack.github.io/docs/tutorials/getting-started/