# Module
```ruby
module Destructable
  def destroy(anyobject)
    puts "I will destroy the object"
  end
end

class Material
  include Destructable
end

# example

```