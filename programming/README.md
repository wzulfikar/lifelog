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


https://github.com/bpampuch/pdfmake/issues/302

get checkbox value: `$('#your-el').is(':checked');`
`$('#your-el').attr('checked', true);`

**supervisor**

- `nano /etc/supervisord.conf`
- `/usr/bin/supervisord -c /etc/supervisord.conf`
- `ps aux | grep php`

**sample supervisor conf file**
```
[supervisord]
logfile=/tmp/supervisord.log  ; (main log file;default $CWD/supervisord.log)
logfile_maxbytes=50MB                    ; (max main logfile bytes b4 rotation;default 50MB)
logfile_backups=10                       ; (num of main logfile rotation backups;default 10)
loglevel=info                            ; (log level;default info; others: debug,warn,trace)
pidfile=/tmp/supervisord.pid  ; (supervisord pidfile;default supervisord.pid)
nodaemon=false                           ; (start in foreground if true;default false)
minfds=1024                              ; (min. avail startup file descriptors;default 1024)
minprocs=200
childlogdir=/tmp

[unix_http_server]
file=/tmp/supervisor.sock

[supervisorctl]
serverurl=unix:///tmp/supervisor.sock

[program:laravel_queue]
command=php /www/laravel_app/artisan queue:work --daemon --env=production --tries=5
user=ioss
stdout_logfile=/www/iossAdmin/storage/logs/ioss_admin_queue.log
redirect_stderr=true
autostart=true
autorestart=true
```

Looks like you runs out of swap memory, try this

/bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=1024

/sbin/mkswap /var/swap.1

/sbin/swapon /var/swap.1


swap problem composer: http://stackoverflow.com/questions/18116261/php-composer-update-cannot-allocate-memory-error-using-laravel-4

https://www.digitalocean.com/community/tutorials/how-to-configure-virtual-memory-swap-file-on-a-vps

https://github.com/facebook/hhvm/issues/1342
    
soft delete: http://stackoverflow.com/questions/18041155/why-soft-deleted-entities-appear-in-query-results


### BEEGO

https://medium.com/@richardeng/a-word-from-the-beegoist-d562ff8589d7#.xj8465coo

http://www.sitepoint.com/go-building-web-applications-beego/

http://www.sitepoint.com/go-building-web-applications-beego-part-2/

http://superuser.com/questions/433746/is-there-a-fix-for-the-too-many-open-files-in-system-error-on-os-x-10-7-1

### Rails
http://guides.rubyonrails.org/getting_started.html
http://stackoverflow.com/questions/15343771/ruby-bundle-install-update-too-slow
https://github.com/bundler/bundler/issues/2125
http://geekmonkey.org/2012/09/introducing-turbolinks-for-rails-4-0/
