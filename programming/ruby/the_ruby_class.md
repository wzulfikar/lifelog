# The Ruby Class

```ruby
class Animal {
    
  attr_accessor :name

  def initialize(name){
    @name = name
  }

  def greet
    puts "Hi there, my name is #{@name}!"
  end

  protected 
    def protected_method
    end

  private
    def private_method
    end
}
```

Above snippet is example of basic Ruby class.

We use `attr_accesor` to access & mutate instance variable instead of writing getter & setter. 