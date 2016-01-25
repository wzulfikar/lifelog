# Draft

Floating ideas, ice box, things that I wanted to write.

- bro syak story with syafi (personal)
- bro syak story of that mosque manager (personal)
- using alinof timer (tech stuff)
- use casperjs to login
    - http://stackoverflow.com/questions/13376189/how-to-login-into-a-website-with-casperjs
    - http://code-epicenter.com/how-to-login-to-facebook-using-casperjs/

https://ghostinspector.com/blog/making-casperjs-tests-more-reliable/

https://scotch.io/tutorials/run-gulp-tasks-in-laravel-easily-with-elixir


https://scotch.io/tutorials/run-gulp-tasks-in-laravel-easily-with-elixir

https://scotch.io/tutorials/automate-your-tasks-easily-with-gulp-js

https://www.npmjs.com/package/gulp-casperjs

http://macr.ae/article/gulp-casperjs.html

http://code-epicenter.com/web-scraping-with-casperjs-handling-pagination/

http://code-epicenter.com/how-to-login-to-twitter-using-casperjs-and-phantomjs-and-extract-tweets/

http://webdriver.io

http://enterprisewebbook.com/ch7_testdriven_js.html

---
- create task to run casperjs test
    - https://www.npmjs.com/package/gulp-casperjs
- add casperjs test to watch
    - https://scotch.io/tutorials/automate-your-tasks-easily-with-gulp-js
    
---

Quick note. Laravel uses app key for encryption. To decrypt an encrypted value, use `Crypt::decrypt($encrypted);`. See: http://laravel-recipes.com/recipes/106/decrypting-a-value.

---
password encrypter http://www.passwordtool.hu

https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-with-nginx-on-ubuntu-14-04

http://aozora.github.io/bootplus/index.html

http://superuser.com/questions/462141/how-to-chown-chmod-all-files-in-current-directory

===
tympanus.net/Development/TooltipStylesInspiration

http://serverfault.com/questions/604316/how-to-change-the-ssh-port-for-a-specific-ip-address

http://nerderati.com/2011/03/17/simplify-your-life-with-an-ssh-config-file/

sudo chmod -R o+w storage

https://laravel.com/docs/5.2/upgrade

realfavicongenerator.net

http://stackoverflow.com/questions/29166030/gitignore-does-not-work-for-subfolder-of-ignored-folder

https://mattstauffer.co/blog/laravel-forge-wildcard-subdomains

https://hackertarget.com/7-nmap-nse-scripts-recon/

http://null-byte.wonderhowto.com/how-to/hack-like-pro-crack-online-web-form-passwords-with-thc-hydra-burp-suite-0160643/


http://laravel.io/forum/12-29-2014-model-observer-problem-in-laravel-5

- go to skolafund.com, pass session id
- login at skolafund.com
- redirect to skolaship, pass username && session id
- check if session id of redirected user is same
- auth::login(username)

ddd may reset session

http://laravel-tricks.com/tricks/easy-eloquent-relation-cache-management

http://stackoverflow.com/questions/19581059/misconf-redis-is-configured-to-save-rdb-snapshots

http://stackoverflow.com/questions/9270734/ssh-permissions-are-too-open-error

aws-ec2-virginia
mysql root `12321`123
redis root 321`12321`

https://www.digitalocean.com/community/tutorials/how-to-configure-a-redis-cluster-on-ubuntu-14-04

https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server

http://askubuntu.com/questions/402980/give-user-write-access-to-folder

1qazxsw21`

https://blog.smalldo.gs/2014/11/laravel-retrieve-fillable-attributes-on-a-model/

awtopup
- when sales happen, assign vouchers.price to sales.voucher_price. this way, voucher price can be updated without losing profit from previous sales
- sku is char 4

- user account

server setup from zero to deployment
nginx + hhvm without php-fpm installed
setup subdomain utamastudio
- awtopup-staging
- akindacargo-staging
- ifa-staging
- omp-staging
- guruqiraati-staging

- create server config in sites-available
- create symlink of above config in sites-enabled
- chown -R www-data:www-data storage

possible issue:
- storage permission
- fastcgi with hhvm
- route not found
http://daylerees.com/nginx-configuration-for-daylerees-dot-com/

root  `123qwer`123

master password aws rds : `12321`123

http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html

http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.CreatingConnecting.MySQL.html

http://www.buzzfeed.com/awesomer/the-best-resumes-any-company-has-ever-received#.ppoqKMyp5

conventions: staging.awtopup

https://kb.iu.edu/d/abnd

http://laravel.io/forum/08-23-2014-return-view-in-json

1qaz2wsx1qaz

$ cd app/storage
$ sudo chmod 777 *
$ sudo chmod 666 */*

http://alanstorm.com/composer_autoloader_features_part_2

fix campaign sponsor cache not being flushed

- get sentiment
- highlight positive with green
- highlight negative with light red

punctuality!
http://www.forbes.com/sites/brentbeshore/2015/08/02/5-minutes-early-is-on-time-on-time-is-late-late-is-unacceptable/

https://github.com/Zizaco/entrust/issues/379

use EntrustUserTrait::can insteadof Authorizable
https://github.com/Zizaco/entrust/issues/371
