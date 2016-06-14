# Rails
- http://www.openvim.com

### Common Command
- `rails s` run rails server. alias: `rails server`
- `rails c` run rails console. alias: `rails console`
- `rails g {options}` run rails generator. alias: `rails generate {options}
- `rails {name of command} -h` display help for given command
- `rake db:migrate` run migration
- `rake db:rollback` rollback migration
- `rake routes` display available routes


>the scaffold generator (`rails g scaffold {model name}`) creates all the parts of the MVC stack.

http://stackoverflow.com/questions/17497012/rails-4-heroku-sqlite3-error

http://stackoverflow.com/questions/392022/best-way-to-kill-all-child-processes

http://stackoverflow.com/questions/4536326/heroku-free-account-limited

_timeout `rake db:migrate`_
- http://stackoverflow.com/questions/14892200/cant-heroku-run-rake-db-migrate-through-my-app  
- http://stackoverflow.com/questions/8582860/heroku-run-console-get-timeout-awaiting-process  
TL;DR `heroku run:detached rake db:migrate
`
http://railsapps.github.io/updating-rails.html

rails 5: https://www.youtube.com/watch?v=OaDhY_y8WTo

upgrade to rails 5: http://edgeguides.rubyonrails.org/upgrading_ruby_on_rails.html

undo code generation using `destroy`:
```
rails generate controller StaticPages home help
rails destroy  controller StaticPages home help
```

http://sublimecodeintel.github.io/SublimeCodeIntel/

http://stackoverflow.com/questions/27047174/rake-aborted-ruby-on-rails