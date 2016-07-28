# My First Ruby Console App

Just started playing around with Ruby, and this is what I did after reading some tutorials. 

A basic console app to demonstrate the use of ruby `hash` to lookup city code based on given city name.

```ruby
dial_book = { 
    "newyork" => "212", 
    "edison" => "908"
}

# extract city names from hash keys
def get_city_names(hash) 
    hash.keys
end

# extract city code names from hash keysdef get_city_code(city_data, city) 
    city_data[city]
end

loop do 
    cities = get_city_names(dial_book) 
    puts "Choose city from list to lookup its code:" 
    puts cities.join "\n"
     
    answer = gets.chomp
     
    if cities.include?(answer) 
        code = get_city_code(dial_book, answer) 
        puts "The code for #{answer} is #{code}" 
    else 
        puts "There's no data for city '#{answer}'" 
    end
end
```
