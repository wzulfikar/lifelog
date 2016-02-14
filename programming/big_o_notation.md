# Big O Notation



Time complexity is a way of discussing how long specific algorithms take. This is useful in streamlining software so it works as fast as possible.

When you're writing code, you should be aware of how long it's going to take to execute. Nobody wants to create a product that users find frustrating due to slow use.

Time complexity is talked about in relation to an algorithm, a collection of one or more functions.


>Big O Notation specifically helps you identify when an algorithm wouldn't 'scale' well, or work well with varying amounts of users, information, or other inputs.

--

>no matter how big and fast your computer is, if the algorithm is ***exponentially inefficient***, it's realistically unusable.

Time complexity is classified by the nature of the function T(n). O represents the function, and (n) represents the number of elements to be acted on.

Worst-case time complexity, the longest it could possibly take with any valid input, is the most common way to express time complexity.

When you discuss Big-O notation, that is generally referring to the worst case scenario.

For example, if we have to search two lists for common entries, we will calculate as if both entries would be at the very end of each list, just to be safe that we don't underestimate how long it could take.

O(1) - determining if a number is odd or even. O(1) is a static amount of time, the same no matter how much information is there or how many users there are.

O(log N) - finding a word in the dictionary (using binary search). Binary search is an example of a type of 'divide and conquor' algorithm.

O(N) - reading a book

O(N log N) - sorting a deck of playing cards (using merge sort)

O(N^2) - checking if you have everything on your shopping list in your cart

O(infinity) - tossing a coin until it lands on heads

>As a rule of thumb, anything with N^2 or any other exponent is NOT a good algorithm for a site with multiple users.

