# Rails
- http://www.openvim.com

### Common Command
- `rails s` run rails server. alias: `rails server`
- `rails c` run rails console. alias: `rails console`
- `rails g {options}` run rails generator. alias: `rails generate {options}
- `rails {name of command} -h` display help for given command
- `rake db:migrate` run migration
- `rake routes` display available routes


>the scaffold generator (`rails g scaffold {model name}`) creates all the parts of the MVC stack.

http://stackoverflow.com/questions/17497012/rails-4-heroku-sqlite3-error

http://stackoverflow.com/questions/392022/best-way-to-kill-all-child-processes

http://stackoverflow.com/questions/4536326/heroku-free-account-limited

_timeout `rake db:migrate`_
http://stackoverflow.com/questions/14892200/cant-heroku-run-rake-db-migrate-through-my-app  
TL;DR `heroku run:detached rake db:migrate
`