# Laravel Schedule Tester

- Save this snippet as file named `ScheduleTester` in `app/Console/Command`.

```php
<?php

namespace App\Console\Commands;

use Illuminate\Console\Command;

class ScheduleTester extends Command
{
  protected $signature = 'schedule:test';

  protected $description = 'Simple test to see if scheduler is working. Check your log file to verify.';

  /**
   * Execute the command.
   *
   * @return void
   */
  public function handle()
  {
    $msg = sprintf('Hello from Laravel Task Schedule Tester! Time is %s.', date('Y-m-d H:i:s (l)'));
    \Log::info($msg);
  }
}
```

- Register above command in `app/Console/Kernel.php` and call it by putting below snippet inside `schedule` method of the `Kernel.php`
file
`$schedule->command('schedule:test')->everyMinute();`

- Execute `php artisan schedule:run` and see check your log
- If you already set the cron for Task Scheduling, wait for one minute and check again your log to verify if cron is working correctly

If you only want to check whether `SchedulerTester` is working or not, execute `php artisan schedule:test`.