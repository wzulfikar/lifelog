# Laravel, Personally.

This is list of things I do/use when building project with Laravel.

- Use [git](https://git-scm.com) for version control
- Use repository layer
- Use interface
- Setup `BaseModel` that extends eloquent model
- Use [postman](https://www.getpostman.com) to test API
- Use [bower](http://bower.io) for fast front-end deployment
- Use `gulp tdd` with [phpunit](https://phpunit.de)
- Use [dropzonejs](http://www.dropzonejs.com)
- Use dropzonejs within form
- Use [jenssegers/laravel-rollbar](https://github.com/jenssegers/laravel-rollbar) for error monitoring using [rollbar](https://rollbar.com)
- Setup registration for *environtment-specific* service providers
- Only report to rollbar in production environment. Because for rollbar free account, it limit the usage to 5000 reports per month.
- Use [newrelic](http://newrelic.com) for performance monitoring
- Use [rap2hpoutre/laravel-log-viewer](https://github.com/rap2hpoutre/laravel-log-viewer) package to view laravel log
- Use [Sami](https://github.com/FriendsOfPHP/Sami) for API documentation generator
- Setup config file for [Sami](https://github.com/FriendsOfPHP/Sami)
- Setup helper file
- Use [itsgoingd/clockwork](https://github.com/itsgoingd/clockwork) to inspect db query, etc.
- Use [yajra/laravel-datatables](https://github.com/yajra/laravel-datatables) for fast datatables deployment
- Use built-in faker and ModelFactory to create dummy data
- Use [momentjs](http://momentjs.com) (date library built on js)
- Use [iTerm](https://www.iterm2.com) or [Conemu](https://conemu.github.io) for command line
- Use [brew (Mac)](http://brew.sh) or [chocolatey (Windows)](https://chocolatey.org) for non-linux package manager
- Use [Intervention/image](https://github.com/Intervention/image) to deal with image processing if any
- Use [Zizaco/entrust](https://github.com/Zizaco/entrust) for Role-Based Access Control (RBAC) if any
- Use [pacejs](http://github.hubspot.com/pace/docs/welcome/) for connection indicator (optional)
- Use [offlinejs](http://github.hubspot.com/offline/docs/welcome/) for offline indicator (optional)
- Use [SequelPro (Mac)](http://www.sequelpro.com) or [Sql Yog Community (Windows)](https://github.com/webyog/sqlyog-community/wiki/Downloads) for MySql client
- Tooltip (eg. [bootstrap tooltip](http://getbootstrap.com/javascript/#tooltips)) to add value for ux