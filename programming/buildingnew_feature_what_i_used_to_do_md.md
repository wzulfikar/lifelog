# Building New Feature : What I used to do.

- Create new branch, e.g: `feature-{feature_name}`
- Use task runner ([gulpfile](http://gulpjs.com), [grunt](http://gruntjs.com), etc) for [tdd](https://en.wikipedia.org/wiki/Test-driven_development)
- Create test file for the feature, e.g: [PHPSpec](http://phpspec.net), [PHPUnit](https://phpunit.de), [Behat](http://behat.org), etc
- Start coding, commit often 😜

Personally, when using Laravel 5 this is what I used to do:
- Create event that will be triggered if the new feature is executed properly
- Create artisan console to execute the new feature
- Create test file
- Start coding for new feature
    - When need to execute new feature, call artisan console
    `Artisan::call('commandName',$argument)`
    - Trigger above event inside artisan console
- When I feel that the code is mature enough, I'll move that code to the respective service provider or repository.

For example, when building user login feature, i'll:
- Create event to determine succesful user login:  
    `artisan make:event UserLoginSucceed`
- Create the console  
`php artisan make:console UserLogin --command user:login`
- Create test file  
`php artisan make:test UserLoginTest`
    - assert that the event is triggered  
    `$this->expectsEvents(UserLoginSucceed::class);`
    - call artisan console
- Put neccessary code for login there, including the trigger for event `UserLoginSucceed`
- When I want to login a user from UserController, I'll *call artisan console*:  
    
```php
// in UserController.php
Artisan::call('user:login', ['user'=>...,'pass'=>...]);
```

>After creating artisan console, don't forget to create new entry for it in `app/Console/Kernel.php`

Following above steps, for each feature I develop I'll have at least an artisan console and an event. This way, I can get some advantages:

- Easier for me to test. Using Laravel, my test will look like this:

```php
// tell the test that we want UserLoginSucceed to be triggered
$this->expectsEvents(UserLoginSucceed::class);

// call artisan console
Artisan::call('customer:deposit',
              compact('username_or_email','amount')
              );
```
- Reusable component: just call artisan console, via terminal or inside your code
- Hookable event: I can tell Laravel to perform other task when the event is triggered
- Can use advantage of `Artisan::queue`
---
Related article:
- [Artisan console: managing exit code](artisan_console_managing_exit_code.md)