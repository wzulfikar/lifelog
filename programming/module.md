# Module
```ruby
# module "Destructable"
module Destructable
  def destroy(obj)
    puts "destroying object.."
  end
end

class Material
  include Destructable
end

# example
table = new Material
table.destroy # "destroying object.."
```

In above snippet, we can call `destroy` method from instance of `Material` class even if we didn't specify the `destroy` method in  `Material` class. This is because we use the definition of `destroy` method via Ruby `module`.

The way it works is, we define set of methods inside module and *include* it in any class, where we want to use it by putting `include` keyword, just like in above snippet.