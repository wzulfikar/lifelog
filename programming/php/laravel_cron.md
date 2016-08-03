# Laravel Cron

- define cron job. assuming u're root, add this code in `etc/crontab` add:

  `* * * * * root php /path/to/artisan schedule:run >> /dev/null 2>&1`
- check cron log: `tail -f /var/log/cron`

sample schedule: 

>*ping every minute to request bin. put the code `app/Console/Kernel.php`, in `schedule()` method.*

```php
$schedule->call(function () {return true;})->everyMinute()->thenPing('http://requestb.in/1cs75qz1');
```

to test in your local machine, execute `php artisan schedule:run`

*Do you know what makes the cron eats CPU?*

## List Cron Entry




http://crontab.guru
http://www.liquidweb.com/kb/how-to-display-list-all-jobs-in-cron-crontab/
