# Inheritance

```ruby
class User
  def initialize(name, email)
    @name = name
    @email = email
  end

  protected
    def protected_method
    end

  private
    def private_method
    end
end

// Buyer inherits User
class Buyer < User

end

// Seller inherits User
class Seller < User

end
```