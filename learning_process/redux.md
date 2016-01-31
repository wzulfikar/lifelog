# Redux

![react-redux-tooling](../images/react-redux-tooling.png)

Basic steps:
- Project files
- Tooling. Output: index.html, application.js, style.css
- Display in browser

>Common Steps:
- `npm install` to install dependencies
- `npm start` to run the start script  
*Dependencies and start script defined in `package.json`*

Components are snippet of code that produce HTML.

The role of webpack and babel is to convert our jsx code into vanilla javascript which browser can understand.

- So why use jsx in the first time?  
To make our code more elligible. Try write a code in jsx and compare to its vanilla javascript version here https://babeljs.io/repl/.

Using javascript module: don't forget to import the component before using it.

- Differentiate between component class & instance  
When not wrapped in jsx tag, it's just a class & not instantiated. When wrapped in jsx, it's becoming an instance. Just the same as calling `React.createElement`.


use `-S` or `--save` switch in `npm install` to save the dependency installed in `package.json`

Saying `import X from 'Y'` will give you whatever object in file Y was exported as the default.

Read mozilla documentation about javascript export:
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export