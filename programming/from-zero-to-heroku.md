# From Zero to Hero(ku)

This is deployment process of Rails app from zero to heroku app. From nothing to something accessible via heroku subdomain: https://your-app-name.heroku.com



pushing without github (only heroku):



- push to heroku

`git push heroku master`



#1 attempt

- Push rejected, failed to compile Ruby app.



-> heroku by default considered as production env



solution to #1 attempt

- move sqlite gem to dev & test group

- create new production group and add pg gem

- exec build i

- gemfile & gemfile.lock is updated, commit the change

- push to heroku



open the app: `heroku open`



-> push not rejected, but now it says "the page you were looking for doesn't exist"



- check log: `heroku logs`

- tail log: `heroku logs -t`

found: ActionController::RoutingError (uninitialized constant WelcomeController):


solution: make welcome controller & its view



-> heroku procfile?



-> read warning & fix



https://devcenter.heroku.com/articles/getting-started-with-rails4



> if this is ur first time using heroku, u may want to add your machine's ssh key to heroku so u don't need to key in email & password everytime u push to heroku. to do that, issue `heroku keys:add`



to rename the app, type `heroku rename (new name)`






