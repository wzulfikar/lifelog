# Programming

Most of the stuff here is basically my personal approach, which might not be best practice for you. Sometimes it just code snippets. 

Anyway, I'm open to any idea, suggestion or comment 😉

https://www.vividcortex.com/blog/2014/01/15/two-go-memory-leaks/

https://blog.rubylearning.com/best-practices-for-a-new-go-developer-8660384302fc#.q3yzzxiur

https://talks.golang.org/2013/bestpractices.slide#2

http://talks.golang.org/2014/go4gophers.slide#6

http://talks.golang.org/2012/splash.article

in golang, interface is instantiable

tour about interface: https://tour.golang.org/methods/10

http://stackoverflow.com/questions/11634809/twitter-bootstrap-focus-on-textarea-inside-a-modal-on-click

```go
// from https://tour.golang.org/methods/10
package main

import "fmt"

type I interface {
	M()
}

type T struct {
	S string
}

// This method means type T implements the interface I,
// but we don't need to explicitly declare that it does so.
func (t T) M() {
	fmt.Println(t.S)
}

func main() {
	var i I = T{"hello"}
	i.M()
}
```

session tracking servlet: 
- http://www.tutorialspoint.com/servlets/servlets-session-tracking.htm
- http://www.wideskills.com/servlets/session-tracking-techniques

laravel cron:
- define cron job. assuming u're root, inside `etc/crontab` add:

  `* * * * * root php /path/to/artisan schedule:run >> /dev/null 2>&1`
- check cron log: `tail -f /var/log/cron`

sample schedule: 

>*ping every minute to request bin. put the code `app/Console/Kernel.php`, in `schedule()` method.*

```php
$schedule->call(function () {return true;})->everyMinute()->thenPing('http://requestb.in/1cs75qz1');
```


get checkbox value: `$('#your-el').is(':checked');`
`$('#your-el').attr('checked', true);`

**supervisor**

- `nano /etc/supervisord.conf`
- `/usr/bin/supervisord -c /etc/supervisord.conf`
- `ps aux | grep php`

swap problem composer: http://stackoverflow.com/questions/18116261/php-composer-update-cannot-allocate-memory-error-using-laravel-4

\DB::enableQueryLog();
    $calItems = CalItem::whereRaw($likeQuery)->get();

    $queries = \DB::getQueryLog();
    $last_query = end($queries);
    dd($last_query);