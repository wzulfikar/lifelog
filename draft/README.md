# Draft

Floating ideas, ice box, things that I wanted to write.

- bro syak story with syafi (personal)
- bro syak story of that mosque manager (personal)
- using alinof timer (tech stuff)
- use casperjs to login
    - http://stackoverflow.com/questions/13376189/how-to-login-into-a-website-with-casperjs
    - http://code-epicenter.com/how-to-login-to-facebook-using-casperjs/

http://pingendo.com vs https://bootstrapstudio.io

javalite.io

gzip: http://askubuntu.com/questions/553158/compressing-a-folder-tar-without-its-containing-directory-in-the-foldername

https://ghostinspector.com/blog/making-casperjs-tests-more-reliable/

https://mattstauffer.co/blog/conditionally-loading-service-providers-in-laravel-5

lodash VS underscore

cloud9 workspace clone nodeschool-challenges

https://c9.io/new/clone?name=nodeschool-challenges-bare-cloned&cloneFromWorkspace=wzulfikar%2Fnodeschool-challenges-bare&description=challenges%20from%20http%3A%2F%2Fnodeschool.io&private=false

email inliner:
- http://templates.mailchimp.com/resources/inline-css/
- http://foundation.zurb.com/emails/inliner.html
- https://inlinestyler.torchbox.com
- https://github.com/Automattic/juice
- https://github.com/remy/inliner

sentiment analysis
http://www.sitepoint.com/creating-sentiment-analysis-application-using-node-js/

learn node workshopper
http://lin-clark.com/blog/2014/07/01/authoring-nodejs-workshopper-lessons/

http://nodeschool.io

semver.org

http://stackoverflow.com/questions/3366895/group-by-month-and-year-in-mysql

bower ubuntu + npm legacy
http://stackoverflow.com/questions/21491996/installing-bower-on-ubuntu

https://vulcanpost.com/540311/new-o-level-subject-computing/

cloudflare certificate
https://blog.cloudflare.com/protecting-the-origin-with-tls-authenticated-origin-pulls/

https://scotch.io/tutorials/run-gulp-tasks-in-laravel-easily-with-elixir


BDD Laravel
https://semaphoreci.com/community/tutorials/getting-started-with-bdd-in-laravel

https://heim.ifi.uio.no/~trygver/2007/MVC_Originals.pdf

android lifecycle

http://www.startandroid.ru/en/lessons/complete-list/232-lesson-24-activity-lifecycle-example-about-changing-states-with-two-activities.html

http://stackoverflow.com/questions/17604232/edit-a-commit-message-in-sourcetree-windows-already-pushed-to-remote

max function nesting reached:
https://laracasts.com/discuss/channels/general-discussion/xdebug-max-nesting-level-reached
http://stackoverflow.com/questions/13213378/what-is-causing-a-maximum-function-nesting-level-error-in-symfony-2-1-and-twig

https://chocolatey.org/about

```
function repeat(str, num) {
  // repeat after me
  var repeat = '';
  while(num > 0){
    repeat += str;
    num--;
  }
  return repeat;
}

repeat("abc", 3);
```

```
function slasher(arr, howMany) {
  // it doesn't always pay to be first
  while(howMany){
    arr.shift();
    howMany--;
  }
  return arr;
}

slasher([1, 2, 3], 2);
```

```
function bouncer(arr) {
  // Don't show a false ID to this bouncer.
  return arr.filter(function(val, key){
    return val || false;
  });
}

bouncer([7, "ate", "", false, 9]);
```

```
//www.freecodecamp.com/challenges/where-do-i-belong
function where(arr, num) {
  // Find my place in this sorted array.
  return arr.concat(num).sort(function(a,b){
    return a - b;
  }).indexOf(num);
}

where([40, 60], 50);
```

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

http://stackoverflow.com/questions/3370334/difference-between-acceptance-test-and-functional-test

http://www.jqueryrain.com/?VAAZCOTI

https://fengyuanchen.github.io/cropper/

https://core.telegram.org/bots/api

https://nicksergeant.com/running-supervisor-on-os-x/

https://github.com/js-cookie/js-cookie

http://7php.com/php-interview-taylor-otwell/

https://laravel-news.com/2015/11/laravel-5-2-a-look-at-whats-coming/

https://github.com/matiassingers/awesome-readme

https://changelog.com/top-ten-reasons-why-i-wont-use-your-open-source-project/

https://www.youtube.com/watch?v=BFeEh3auyDQ

http://socialiteproviders.github.io

https://medium.com/laravel-news/adding-auth-providers-to-laravel-socialite-ca0335929e42#.k1xe4gwtc

http://www.codeanchor.net/blog/creating-custom-laravel-5-packages/

http://laravel.io/forum/03-24-2015-how-to-register-console-command-from-package-in-laravel-5

http://stackoverflow.com/questions/23063240/laravel-cookieforget-doesnt-work

aboud SOLID design principle

https://regex101.com/#javascript

http://ogp.me


edit gulp notify (laravel-elixir/notification.js)
https://laracasts.com/discuss/channels/elixir/laravel-elixir-gulp-notifications

https://moroccojs.org/tutorials/npm-based-front-end-workflow/

https://github.com/dypsilon/frontend-dev-bookmarks

http://stackoverflow.com/questions/11025980/how-to-add-usr-local-bin-in-path-on-mac

http://www.science.co.il/Language/Locale-codes.asp


http://www.sitepoint.com/8-must-have-php-quality-assurance-tools/

https://nicksergeant.com/running-supervisor-on-os-x/

http://supervisord.org

http://www.creativebloq.com/typography/best-handwriting-fonts-12121527

https://medium.com/@fat/mediums-css-is-actually-pretty-fucking-good-b8e2a6c78b06#.f4ply3oae

http://vegibit.com/laravel-repository-pattern/

http://pingturtle.com/home/post/cloudflare-email-protection-decoder


http://checkgzipcompression.com

http://stackoverflow.com/questions/24585261/nvm-keeps-forgetting-node-in-new-terminal-session

http://benmccormick.org/2015/01/22/is-bower-useful/

- Nginx with pretty domain: http://zaiste.net/2013/03/serving_apps_locally_with_nginx_and_pretty_domains/

http://blog.namangoel.com/a-javascript-developers-take-on-swift

http://www.mrspeaker.net/2014/06/04/selling-swift/

http://0.30000000000000004.com

https://medium.com/javascript-scene/the-two-pillars-of-javascript-ee6f3281e7f3#.ugymz7aro
- Code is the tool. The program is the product.
- Yes, some code is art in and of itself, but if it doesn’t stand alone published on paper, your code doesn’t fall into that category.

**HipHop Fatal error: unexpected St13runtime_error: locale::facet::_S_create_c_locale name not valid**
- http://www.inmotionhosting.com/support/website/ssh/speed-up-grep-searches-with-lc-all
- https://github.com/facebook/hhvm/issues/1052


http://nerds.airbnb.com/isomorphic-javascript-future-web-apps/

https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm

- OSCON 2014: How Instagram.com Works; Pete Hunt  
https://www.youtube.com/watch?v=VkTCL6Nqm6Y&feature=youtu.be

- webpack: https://www.youtube.com/watch?v=TaWKUpahFZM

Testing with Casper JS:
- http://docs.casperjs.org/en/latest/testing.html#testing
- https://www.lullabot.com/articles/testing-the-front-end-with-casperjs
- http://www.helpscout.net/blog/functional-testing-casperjs/

Installing Casper JS using git:
- http://docs.casperjs.org/en/latest/installation.html

Other method of installation (Casper JS):
- http://docs.casperjs.org/en/latest/installation.html#installing-from-git

- Casper JS installation:
 - Install phantom js: download phantomjs from its website and symlink to your path
 - Install casper js using git : http://docs.casperjs.org/en/latest/installation.html#installing-from-git
 
http://glenmaddern.com/articles/css-modules

http://laravel.io/forum/05-08-2014-failed-to-open-stream-permission-denied

http://adrianmejia.com/blog/2014/10/01/creating-a-restful-api-tutorial-with-nodejs-and-mongodb/

https://en.wikipedia.org/wiki/User_story


> In computer science, data is anything that is meaningful to the computer. JavaScript provides seven different data types which are undefined, null, Boolean, string, symbol, number, and object.

```javascript
var array = [4,5,6,7,8];
var singleVal = 0;

// Only change code below this line.

singleVal = array.reduce((a, b)=> a + b);
```

Sort array
```javacscript
[1, 12, 21, 2].sort((a,b)=>b-a);
```

http://gunnariauvinen.com/difference-between-concat-and-push-in-javascript/

```javascript
function factorialize(num) {
  return num == 1 || num === 0 ? 1 : num * (factorialize(num-1));
}

factorialize(5);
```

JS apply function
http://stackoverflow.com/a/1379560


http://choosealicense.com
## Nodemon
- https://github.com/remy/nodemon
- http://nodemon.io

## NodeJS Framework
List :  
- [Express JS](http://expressjs.com)
- [Sails JS](http://sailsjs.org)
- [Hapi JS](http://hapijs.com)
- [Mullet](http://mullet.io)
- [Aqua (Hapi Boilerplate)](http://jedireza.github.io/aqua/)
- [Hapi + Socket.io](https://github.com/dwyl/hapi-socketio-redis-chat-example)
- [Kraken](http://krakenjs.com)
- [Loopback](http://loopback.io)
- [Meteor JS](https://www.meteor.com)

## Meteor JS
- https://blog.tableflip.io/large-meteor-projects-best-practices/

>`id` attributes should be unique. Browsers won't enforce this, but it is a widely agreed upon best practice. 

- Using hex for color (freecodecamp) : http://www.freecodecamp.com/challenges/use-hex-code-to-color-elements-red#
- Abbrevi