# React JS

## Intro
- [github.com/stephengrider/reactcasts]()
- ste.grider@gmail.com

## JSX
- Extension of javascript
- Write html inside javascript
- JSX needs to be compiled into javascript before running
- XML-like syntax extension to ECMAScript without any defined semantics. It's NOT intended to be implemented by engines or browsers. [https://facebook.github.io/jsx/]()

Example:

```js
{
    render:function(){
        // javascript
        var a = 1;
        console.log(a + 1);
        
        // JSX
        return (
        <div>
            Hello world!
        </div>
        );
    }
}
```

When compiled to js, the above example will be:

```js
{
    render:function(){
        var a = 1;
        console.log(a + 1);
        
        return React.createClass('div', null, 'Hello World!');
    }
}
```

## HTML Boilerplate
- Install react library: React, ReactDom & JSX
    - https://facebook.github.io/react/downloads.html
    - https://fb.me/JSXTransformer-0.12.2.js

```js
<!-- via head -->
<script src="https://fb.me/react-0.14.6.js"></script>
<script src="https://fb.me/react-dom-0.14.6.js"></script>
<script src="https://fb.me/JSXTransformer-0.12.2.js"></script>
```

- use `text/jsx` as script type

```php
<script type="text/jsx">
  // TODO:
  // 1. Define react component class
  // 2. Ask react to create element from the class
  // 3. Tell react to render the element & where to put it
</script>
```

> React class must contain `render` method

Example:

```html
<script type="text/jsx">
  // 1. Define react component class
  var HelloWorld = React.createClass({
    render:function(){
        return <div>
            Hello World!
        </div>
    }
  });
	
  // 2. Ask react to create element from the class
  var element = React.createElement(HelloWorld);
	
  // 3. Tell react to render the element & where to put it
  ReactDom.render(element, document.body);
</script>
```
Or, if you want to skip step 2:

```html
<script type="text/jsx">
  // 1. Define react component class
  var HelloWorld = React.createClass({
    render:function(){
        return <div>
            Hello World!
        </div>
    }
  });

  // 3. Tell react to render the class & where to put it
  ReactDom.render(<HelloWorld/>, document.body);
</script>
```

https://github.com/talyssonoc/react-laravel

https://christianalfoni.github.io/react-webpack-cookbook/Structuring-configuration.html

http://ricostacruz.com/cheatsheets/react.html

Even though `React` is not called in script, `import React from 'react'` statement is still required as long as we have jsx inside. Because, behind the scene, thus HTML codes inside jsx will be translated into `React.createElement({...})`.

Code styles:

```javascript
// non-class syntax
export default () => {
	return <input/>
}

// class syntax
export default class NameOfComponent
{
  // `render` method is required in every react class
  render()
  {
    return <input/>
  }
}
```