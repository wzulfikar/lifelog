# React JS

## Intro
- [github.com/stephengrider/reactcasts]()
- ste.grider@gmail.com

## JSX
- Extension of javascript
- Write html inside javascript
- JSX needs to be compiled into javascript before running
- XML-like syntax extension to ECMAScript without any defined semantics. It's NOT intended to be implemented by engines or browsers. [https://facebook.github.io/jsx/]()


## Pete Hunt: React - Rethinking Best Practices 
*JSConf.asia 2013*
- Templates encourage a poor separation of concerns. And so are Angular-style directives
- Templates separate technology, not concerns. And they do it by being deliberately underpowered
- "View-Model" tightly couples template to display logic
- Display logic & markup are highly cohesive: they both show the UI
- The framework cannot know how to separate your concerns for you: it should only provide powerful, expressive tools for the user to do it correctly
- Use components to separate your concerns. With the *full-power* of JavaScript, not a crippled templating language. *And that's how React works*
- Components are reusable, composable & unit testable
- JSX is an ***optional*** preprocessor to let you use HTML-like syntax: it's easy for designers to contribute code
- React: the accessibility of templates and the power of JavaScript
- When the data changes, React re-renders the entire component. Re-rendering on every change makes things simple: every place data is displayed is guaranteed to be up-to-date
- React describe your UI at any point in time, just like a server-rendered app
- Re-render on every change, that seems expensive. Yes, we can't do that re-render things in real browser DOM. That's why we built *Virtual DOM* (and event system)


- Pete Hunt leaves FB:
https://www.facebook.com/429297/posts/10101869605197995

>*What about spaghetti code?*  
Just don't write spaghetti code. Only put display logic in yourcomponents.

- React's Design
 - Re-render the whole app on every update

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

http://www.christianalfoni.com/articles/2015_04_19_The-ultimate-webpack-setup

Even though `React` is not called in script, `import React from 'react'` statement is still required as long as we have jsx inside. Because, behind the scene, thus HTML codes inside jsx will be translated into `React.createElement({...})`.

Code styles:

```javascript
// non class-based syntax (functional component)
export default () => {
	return <input/>
}

// class-based syntax
import React, {Component} from 'react'

export default class NameOfComponent extends Component
{
  // `render` method is required in every react class
  render()
  {
    return <input/>
  }
}
```

>JavaScript classes are introduced in ECMAScript 6 and are *syntactical sugar* over JavaScript's existing prototype-based inheritance

Read more about javascript classses here :
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes

## Unidirectional Data Flow
In React, application data flows unidirectionally via the state and props objects, as opposed to the two-way binding of libraries like Angular. This means that, in a multi component heirachy, a common parent component should manage the state and pass it down the chain via props.

https://medium.com/javascript-scene/the-two-pillars-of-javascript-ee6f3281e7f3#.ugymz7aro

http://www.funnyant.com/reactjs-what-is-it/