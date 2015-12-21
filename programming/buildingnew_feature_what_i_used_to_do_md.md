# Building New Feature : What I used to do.

- Create new branch, e.g: `feature-{feature_name}`
- Create test file for the feature, e.g: [PHPSpec](http://phpspec.net), [PHPUnit](https://phpunit.de), [Behat](http://behat.org), etc
- Use task runner ([gulpfile](http://gulpjs.com), [grunt](http://gruntjs.com), etc) for [tdd](https://en.wikipedia.org/wiki/Test-driven_development)
- Start coding, commit often 😜

When using Laravel, I used to do this when I reach the *start coding* part:
- Create event that will be triggered if the new feature is executed properly
- Create artisan console  
    `artisan make:console UserLogin --command 'user:login'`
- Develop code for the new feature there
- When need to execute new feature, call artisan console
    `Artisan::call('commandName',$argument)`
- When I feel that the code is mature enough, I'll move that code to the respective service provider or repository.

For example, when building user login feature, i'll:
- Create event to determine succesful user login:  
    `artisan make:event UserLoginSucceed`
- Create the console  
`php artisan make:console UserLogin --command user:login`
- Put neccessary code for login there, including the trigger for event `UserLoginSucceed`
- When I want to login a user from UserController, I'll:  
    
```php
// in UserController.php
Artisan::call('user:login', ['user'=>...,'pass'=>...]);
```

>After creating artisan console, don't forget to create new entry for it in `app/Console/Kernel.php`