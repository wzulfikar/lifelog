# My First Ruby Console App

Just started playing around with Ruby, and this is what I did after reading some tutorials. 

A basic console app to demonstrate the use of ruby `hash` to lookup city code based on given city name.

To run the program, you've to install `ruby` in your computer. If you're not sure, just open your terminal/shell/cmd and issue this command `ruby -v`. If `ruby` is installed, the command will display version of your `ruby`. 

Then, put below code to a file named (for example) `city_code.rb` and execute the file `ruby /path/to/city_code.rb`.

### The Code
```ruby
dial_book = { 
    "newyork" => "212", 
    "edison" => "908"
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
