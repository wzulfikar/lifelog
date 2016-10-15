# Setting Multiple Heroku Config Using Terminal

the command to set heroku config is `heroku config:set`. to setup multiple config, separate with whitespace, eg. `heroku config:set KEY_ONE=VALUE_ONE KEY_TWO=VALUE_TWO`. however, this format is hard to read & change when the there are many config vars. to separate thus config vars into lines, we use `\`.

the `\` (backslash) tells terminal to break the line. notice that there's a whitespace before `\`. last entry for config var has no trailing `\`

```
heroku config:set \
KEY_ONE=VALUE_ONE \
KEY_TWO=VALUE_TWO \
KEY_THREE=VALUE_THREE \
LAST_KEY=LAST_VALUE
```
try copy and paste above code in your terminal. remember that you can only execute heroku command `heroku config:set` inside directory of heroku app. 

![heroku config:set](/assets/Screen Shot 2016-10-15 at 2.41.30 PM.jpg)

> to check available heroku apps in your machine, use `heroku apps`.

another example is when you want to set config for laravel app:

```
heroku config:set \
APP_ENV=local \
APP_DEBUG=true \
APP_KEY=DmRe0WkSOdiHpaNaUMD1jv4Wynpi1yPL \
BASE_URL=http://mywebsite.com \
DB_HOST=localhost \
DB_DATABASE=imaluum \
DB_USERNAME=root \
DB_PASSWORD=toor \
CACHE_DRIVER=redis \
SESSION_DRIVER=redis \
QUEUE_DRIVER=sync \MAIL_DRIVER=smtp \MAIL_HOST=smtp.mailgun.org \
MAIL_PORT=587 \
MAIL_USERNAME= \
MAIL_PASSWORD= \
MAILGUN_DOMAIN= \
MAILGUN_SECRET= \
ROLLBAR_TOKEN_SERVER=a67af30e00b641d2995213e7e38d5ee9 \
ROLLBAR_TOKEN_CLIENT=86ca8f9996f349ab9c52e0391ea2f27f \
LOG=errorlog \
LOG_SETTING=daily
```
