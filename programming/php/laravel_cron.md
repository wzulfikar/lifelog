# Laravel Cron

- define cron job. assuming u're root, inside `etc/crontab` add:

  `* * * * * root php /path/to/artisan schedule:run >> /dev/null 2>&1`
- check cron log: `tail -f /var/log/cron`

sample schedule: 

>*ping every minute to request bin. put the code `app/Console/Kernel.php`, in `schedule()` method.*

```php
$schedule->call(function () {return true;})->everyMinute()->thenPing('http://requestb.in/1cs75qz1');
```

*Do you know why, sometimes, the cron eats CPU?*