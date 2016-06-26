> # Rails
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

https://blog.heroku.com/archives/2016/5/9/real_time_rails_implementing_websockets_in_rails_5_with_action_cable

http://stackoverflow.com/questions/4601498/what-is-the-point-of-return-in-ruby

http://www.randomhacks.net/2007/01/20/13-ways-of-looking-at-a-ruby-symbol/

http://www.postpostmodern.com/2009/02/20/a-body-with-class/

admin lte height shrinked: https://github.com/almasaeed2010/AdminLTE/issues/563

- turbolink indicator:
  -  http://stackoverflow.com/questions/18321131/how-to-create-a-youtube-style-loading-bar-with-rails-4s-turbolinks
  -  tl;dr add `Turbolinks.enableProgressBar();` to `application.js`

devise:
https://www.sitepoint.com/devise-authentication-in-depth/

railsapps.github.io/rails-html5-boilerplate.html

https://www.youtube.com/watch?v=qf6abZeAJh4

http://momolog.info/2010/10/07/ruby-map-array-to-hash/

http://www.thegreatcodeadventure.com/here-today-still-here-today-using-gon-with-javascript-and-rails/

trailblazer.to/gems/cells/rails.html

> SCSS only adds features to CSS, rather than defining an entirely new syntax.13 This means that every valid CSS file is also a valid SCSS file, which is convenient for projects with existing style rules.

-

> We can see what happens without a save by using reload, which reloads the object based on the database information

`update_attribute` != `update_attributes`

`validates :email, presence: true`

http://www.rubular.com

regex VALID_EMAIL_REGEX is a constant, indicated in Ruby by a name starting with a capital letter

> to make a user with the same email address as @user using @user.dup, which creates a duplicate user with the same attributes

>  Unfortunately, based on the naïve data model, the only way to find a user by email address is to look through each user row in the database and compare its email attribute to the given email—which means we might have to examine every row (since the user could be the last one in the database). This is known in the database business as a full-table scan, and for a real site with thousands of users it is a Bad Thing.

create index for user email: `add_index :users, :email, unique: true

The way to do this is with a callback, which is a method that gets invoked at a particular point in the lifecycle of an Active Record object.`

> The way to do this is with a callback, which is a method that gets invoked at a particular point in the lifecycle of an Active Record object.

-

> has_secure_password automatically adds an authenticate method to the corresponding model objects. This method determines if a given password is valid for a particular user by computing its digest and comparing the result to password_digest in the database.

*Defining a database index improves lookup efficiency while allowing enforcement of uniqueness at the database level.*

`<%= debug(params) if Rails.env.development? %>`

- scss features:
  - variable
  - nesting
  - mixin

https://github.com/awesome-print/awesome_print

http://stackoverflow.com/questions/7154664/ruby-sqlite3busyexception-database-is-locked

> `has_secure_password` does a lot of things.

- http://devcenter.heroku.com/articles/ssl
- https://devcenter.heroku.com/articles/deploying-rails-applications-with-the-puma-web-server

http://stackoverflow.com/questions/23034863/install-elasticsearch-1-1-using-brew

https://www.railstutorial.org/book/following_users

http://codeloveandboards.com/blog/2014/08/24/rails-and-react-i-a-happy-medium/

http://rails-and-react-iii.herokuapp.com

https://medium.com/@cblavier/rails-with-no-js-framework-26d2d1646cd#.p7s8bltty

http://joshsymonds.com/blog/2012/12/18/making-your-web-pages-ridiculously-fast-without-breaking-them/

https://richonrails.com/articles/mongodb-and-rails

https://richonrails.com/articles/background-tasks-with-rufus-scheduler

https://richonrails.com/articles/rails-presenters

https://richonrails.com/articles/sortable-table-columns

https://richonrails.com/articles/getting-started-with-mysql-and-ruby-on-rails

https://richonrails.com/articles/basic-subdomains-in-ruby-on-rails

https://richonrails.com/articles/downloading-files-via-ftp-using-ruby

https://richonrails.com/articles/outputting-xml-using-ruby-on-rails

https://richonrails.com/articles/seeding-your-database-with-seed-fu

https://richonrails.com/articles/shortening-urls-with-bit-ly

https://richonrails.com/articles/sitemaps-in-ruby-on-rails

https://richonrails.com/articles/sending-sms-using-text-magic

https://github.com/stympy/faker

https://richonrails.com/articles/endless-scrolling