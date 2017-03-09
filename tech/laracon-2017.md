# Laracon 2017 - The First Laravel Online Conference
***Wed, 8 Mar 2017, 8am PST***

## Jeff's Talk
> Wed, 8 Mar 2017 at 22:05:15 MYT

### Webpack
- gulp is task runner, webpack isn't
- webpack 2 is used throughout the slides
- webpack: single entry point
- jeff uses npm for everything
- webpack will assume everything comes across is javascript unless we tell otherwise, and we do so by using loader.
- "loader can transform any file that matches a certain criteria" – Jeff
- you can pull loader from npm. for example, to pull `css-loader`, do this:
  `npm install css-loader --save-dev`
- "plugins are the backbone of webpack. webpack itself is built on this same plugin system"
- tree shaking: remove unused code
- example:

```
npm install webpack --save-dev
webpack src/main.js dist/bundle.js
```

put the webpack in `package.json` to make your life easier. exec `npm run dev` to run it.

```
"scripts": {
    "dev": "webpack src/main.js dist/bundle.js"
}
```

### Laravel Mix
- laravel mix helps you configuring webpack
- mix covers 80% use case, and very likely you're part of that 80% so you can take advantage of mix
- "Laravel doesn't care which js framework you use, if any" – Jeff
- to override webpack config, pass your config to 
`mix.webpackConfig({your_webpack_config_here})`

## Evan's Talk
> Wed, 8 Mar 2017 at 23:05:05 MYT

### Inside Vue Templates
- vue uses *virtual dom*
- browser native dom object is expensive to create & access
- "(Essentially) A lightweight JavaScript data format to
represent what the actual DOM should look like at a
given point in time"
- "Decouples rendering logic from the actual DOM - enables
rendering capabilities in non—browser environments,
e.g. server—side and native mobile rendering."
- Vue Template Explorer: [https://vue-template-explorer.now.sh]()
- Vue collaborate with Alibaba to create cross-platform native framework based on vue js ([Weex](https://github.com/alibaba/weex))
- Link to slide: https://docs.google.com/presentation/d/1jqxl5j2Z7v_Ykd1B-8QrJXiOzHHytu5iqRskYLgyp6k/edit?usp=sharing

## Rachel Andrew's Talk
> Thu, 9 Mar 2017 at 0:19:08 MYT

### About Rachel
- Co-founder Perch CMS: https://grabaperch.com
- @rachelandrew

### CSS Layout
- separation of source & display
- flexbox: you can set order of your elements
- adding `display: flex` to element's container causes the items to display *flexibly* in a row
- CSS Grid automatic placement: 
  - https://rachelandrew.co.uk/archives/2015/04/14/gr‘id-Iayout-
automatic-placement-and-packing-modes/
  - http://www.w3.org/TR/2015/WD-css-grid-1-20150917/#grid-auto-
flow-property
- *with great power comes responsibility*
- recommended video on accessibility: https://vimeo.com/180566024

>**CSS Box Alignment Module Level 3**
“This module contains the features of 088 relating to the
alignment of boxes within their containers in the various 088 box layout models: block layout, table layout, flex layout, and grid layout.” - https://drafts.csswg.org/css-align/

- the new stuffs, grid & flex, will be responsive by default
- flexbox tester: https://madebymike.com.au/demos/flexbox-tester/
- CSS Grid layout unit: `fr` (fraction unit)
- use `minmax(min, max)` to define the minimum & maximum size of element
- IE and Edge still use their early implementation iof CSS Grid Layout
- Feature Queries (`@supports`) →  test for support of property: value pairs
- vertical-align has no effect on a grid item
- items set to display: inline-block or block become grid items
- if grid tracks or flex-basis seem tobeusing a size you didn't expect, *check your item widths*
- for anything ***new*** in CSS, you can use feature queries (`@supports`) to detect support
- slides: https://rachelandrew.co.uk/speaking/event/laracon-online

## Adam Wathan's Talk, Laracon 2017
> Thu, 9 Mar 2017 at 1:18:49 MYT

### TDD - Test Driven Development
- Almost all of your tests should be unit tests
- Your tests should never touch the database
- write a failing test → make the test pass → refactor
- use `Mockery` to mock class
- don't worry about isolation. introduce boundaries when it solves real problem
- contact adam: @adamwathan, adamwathan.me

## Taylor Otwell's Talk, Laracon 2017
> Thu, 9 Mar 2017 at 2:34:10 MYT

- created laravel back in 2007
- laravel has 2 kernels: http & console kernel
- use this if you want to pull container manually: `$container = new Illuminate\Container\Container`
- `Illuminate\Http\Request::capture()` captures request from php, like `$_POST`, `$_GET`, etc
- middleware is sort of revolution of laravel filter
- be cautious where you are in your app lifecycle when you want to use `Auth::user()`
- if necessary, you can override `$bootstrappers` in your artisan console

## Postmark
> Thu, 9 Mar 2017 at 3:28:02 MYT

contact Nick: @nick_canz, nick@widlbit.com

### What developers need to know about email
- what's `MX` records? special type of DNS record (MX, not TXT)
- how's an email formatted? Headers, Body, Attachments.
- Headers =  metadata
- analyse email header: https://toolbox.googleapps.com/apps/messageheader
- X-Headers: custom data stored in heade
- rs like `x-user-id`, `x-spam-flag`, etc
- everything after new line is considered as body (not header anymore)
- most browser & app renders raw html email
- email clients are not HTML5 ready
- check these email templates: https://github.com/wildbit/postmark-templates
- Base64 encoding file can increase size by 30%
- email authentication methods: SPF, DKIM & DMARC
    - spoofing protection
    - deliverability
- SPF: Sender Policy Framework, domain-based way to say what IPs are allowed to send email for you
  - whitelist & blacklist of email domain
  - only 1 DNS record. if more, the check will fail
- DKIM: Message-based signatures to verify your email is unmodified
- DMARC - Domain-based wat to tell receivers how to handle authentication failures for your domain
  - the latest from other 2 authentication methods
  - checking email validity: SPF, DKIMI, DMARC
- major features of email
  - bounces - need to know why you can't contact your customer
  - opens - little pieces of info can have high impact
  - inbound - closing the email "loop" to provide the highest level of interactivity
  - using image to trigger email.open event isn't 100% reliable, but most of the time is.

## JMac, Laracon 2017
> Thu, 9 Mar 2017 at 4:47:37 MYT

### About Jason
- created laravel shift

### You don't know Git
#### Unfamiliar Commands
- `git add` → try `git add -p`
- `git stash --include-untracked`
- `git stash list`
- `git rebase -i`
- `git cherry-pick` - like a transplant
- `git bisect` - systematically move thru commit and prompt you if it's good or bad commit
- `git reflog` - not really stable

#### Common Workflows
- `git flow`

#### Helpful Info
- you may want to create system-wide aliases for git

## Matt Stauffer, Laracon 2017
> Thu, 9 Mar 2017 at 5:35:16 MYT

### About Matt
- created laravel news

### Mastering Illuminate Container
- what is the container == what is Laravel
- the container is essentially the backbone of every laravel app
- without container, laravel app is just set of packages. the container is the glue that tied thus packages together
- container is the tool that enabl DI & IOC
  - **DI** (Dependency Injection) - when one object supplies (injects) the dependencies of another object
  - **IOC** (Inversion of Control) - defining (once) at the framework level how to implement specific features or code paths instead of (multiple times) in the code
- container flow: binding & resolving
- get instance of laravel container: `$container = app()`
- shortcut to get container: `app(CONTAINER_CLASS_HERE)`
- *autowiring* is the reason we use `app(Thing::class)` over `new Thing`

> ***Autowiring is..***
A framework/package's ability to instantiate a class without being given explicit instructions from the user of how to instantiate that class.
If a class has dependencies, an autowiring framework will use reflection to determine and provide its dependencies.

- you can do manual binding when necessary

```php
// binding to container
app()->bind(MyServiceContainer::class, function () {
    return new MyService('sdf89asdl23');
});

// this will return instance of MyService
$service = app(MyServiceContainer::class);
```

- bind and autowiring generates new instance. to get same instance, use `app()->singleton(...)` or `app()->instance(...)`
- alias: bind a string key to another string key

```php
// define alias for MyClass
app()->alias(MyClass::class, 'my_class');

// this will return instance of MyClass::class
$myClass = app('my_class');
```

- laravel uses a lot of aliases in its codebase. you can see thus aliases inside `config/app.php`
- you can use container to resolve a method, eg. `app()->call('SuperClient@get', ['/posts/2'])`, `app()->call([$this, 'doSomethingWithDependencies'])`

### What is Service Providers?
- central location to bind services for use by your application's code, usually grouped by functionality; the place where all of laravel's bootstrapping takes place
- it does thus kind of gross, repeatitive tasks to prepare the code/app
- anatomy of a service provider
  - register - binding the container
  - boot - called after all registrations are completed
  - defer - don't run the service provider until certain bindings are requested
  - provides - if deferred, which bindings request should trigger running this service provider?
- service provider is the hook for 3rd party package to interact with laravel app

### Facades
> **What is Facade?**
A convenience class providing static access to non-static methods on classes resolved out of the container.

- to create facade from any class, bind the class with container and create a class that extends `Facade` which return the container
- laravel 5.4 also provider *real-time* facade

### Miscellanous
- you can bind arbitrary value in container, eg. array of countries which bound to `countries` so you can call `app('countries')` from anywhere
- container also support *contextual binding*
