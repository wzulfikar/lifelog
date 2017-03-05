# Telegram Bot

Another messaging platform [Telegram](https://telegram.org) that offer programmable bot. The bot uses HTTP API, and its endpoint is:

> [https://api.telegram.org/bot{your\_bot\_token}/{commandName}]()

_You can find list of available command here: _[_https://core.telegram.org/bots\#commands_]()

### What I did to set up my first bot..

Talk to [BotFather](https://telegram.me/botfather) using your Telegram account, send him a message “`/newbot`” and then he'll guide you from there. To display things you can do with [BotFather](https://telegram.me/botfather), send him “`/help`”.

![BotFather](../images/botfather.png\)
![BotFather Help]\(../images/botfather-help.png)

Once the new bot is created, you can test it by visiting this url:

[https://api.telegram.org/bot{your\_bot\_token}/getMe]()

Using `getMe` command will return information about your bot. Something like this:

```json
{"ok":true,"result":{"id":"bot_id","first_name":"bot_first_name","username":"bot_username"}}
```

To test whether the bot can receive message, try sending a message to `@your_bot_name` from your telegram account then visit this url:

[https://api.telegram.org/bot{your\_bot\_token}/getUpdates]()

It will display things sent to your bot in JSON format. To dig deeper, you can visit official documentation for Telegram bot here:

> [https://api.telegram.org/bots]()

By the way, in case you're into PHP, someone made SDK here: [https://irazasyed.github.io/telegram-bot-sdk]()

Happy coding 😁 !



## Updates

Sun, 5 Mar 2017 at 23:18:36 MYT

Another awesome bot framework for PHP! Using this framework, you can create bot of multiple platform \(messenger, telegram, etc\). Check this out: http://botman.io

