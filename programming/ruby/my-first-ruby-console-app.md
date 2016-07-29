# My First Ruby Console App

Just started playing around with Ruby, and this is what I did after reading some tutorials.

A basic console app to demonstrate the use of ruby `hash` to lookup city code based on given city name.

To run the program, you've to install `ruby` in your computer. If you're not sure, just open your terminal\/shell\/cmd and issue this command `ruby -v`. If `ruby` is installed, the command will display version of your `ruby`.

Then, put below code to a file named \(for example\) `city_code.rb` and execute the file `ruby /path/to/city_code.rb`.

## The Code

```ruby
dial_book = { 
    "newyork" => "212", 
    "edison"  => "908"
}

# extract city names from hash keys
def get_city_names(hash) 
    hash.keys
end

# extract city code names from hash keys
def get_city_code(city_data, city) 
    city_data[city]
end

loop do 
    cities = get_city_names(dial_book) 
    puts "Choose city from list to lookup its code:" 
    puts cities.join "\n"

    answer = gets.chomp

    if cities.include?(answer) 
        code = get_city_code(dial_book, answer) 
        puts "\n\nThe code for #{answer} is #{code}\n\n" 
    else 
        puts "\n\nThere's no data for city '#{answer}'\n\n" 
    end
end
```

## Screenshot

![](/images/city_code_console.png)

## Still want more?

Let's explain what happens in the code. 

The `dial_book` variable is a ruby hash, where we can store pairs of key & value. In ruby, the `=>` inside hash can be referred as _hash rocket_.

Method in ruby started with `def methodname(param)` keyword and ended with `end` keyword.

In above code, we defined a method called `get_city_names` which accepts single parameter called `hash`.

> `cities.include?` – _notice the question mark there_. 

This is a _**convention**_ in ruby world. Method that returns boolean will have quesetion mark (`?`) at the end of its name.

When calling a method, we can omit the bracket for parameter. So, instead of writing `cities.include?(answer)` we can write `cities.include? answer`. Whichever we feel comfortable. Nice isn't it?

