# Backbone JS

#### backbone stuffs
- https://github.com/marioizquierdo/jquery.serializeJSON
- http://awkward.github.io/backbone.modal/


https://bootstrap-datepicker.readthedocs.org/en/latest/

```
// create user model
User = Backbone.Model.extend({
  // set default values
  defaults:{
    name:null,
    city:null
  }
});

// create new user
var user = new User({
  name:'John Doe',
  city:'New Jersey'
});

// display user info
console.log(user.get('name')); // John Doe
console.log(user.get('city')); // New Jersey
console.log(user.attributes); // {name:'John Doe, city:'New Jersey'}

// update user info
user.set({name:'John Cena'});
```