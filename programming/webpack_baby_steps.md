# Webpack Baby Steps

https://webpack.github.io/docs/tutorials/getting-started/

https://medium.com/@dtothefp/why-can-t-anyone-write-a-simple-webpack-tutorial-d0b075db35ed#.4yc0vsdri

webpack will analyze your entry file for dependencies to other files. These files (called modules) are included in your bundle.js too. webpack will give each module a unique id and save all modules accessible by id in the bundle.js file. Only the entry module is executed on startup. A small runtime provides the require function and executes the dependencies when required.

https://webpack.github.io/docs/tutorials/getting-started/

webpack can only handle JavaScript natively, so we need the css-loader to process CSS files. We also need the style-loader to apply the styles in the CSS file.


We don’t want to write such long requires require("!style!css!./style.css");.

We can bind file extensions to loaders so we just need to write: require("./style.css")

---
>If they go to another page, they don't redownload common code.

It's like browserify but can split your app into multiple files. If you have multiple pages in a single-page app, the user only downloads code for just that page. If they go to another page, they don't redownload common code.

It often replaces grunt or gulp because it can build and bundle CSS, preprocessed CSS, compile-to-JS languages and images, among other things.

###Optimization your bundles
- Reduce number of http request
- Reduce number of bytes downloaded

CSS: Happy global namespace – Pete Hunt


https://github.com/webpack/webpack-dev-server/issues/24