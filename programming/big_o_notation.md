# Big O Notation

*From http://www.freecodecamp.com/videos/big-o-notation-a-few-examples*

**Time complexity** is a way of discussing how long specific algorithms<sup>[1](#1)</sup> take. This is useful in streamlining software so it works as fast as possible.

When you're writing code, you should be aware of how long it's going to take to execute. Nobody wants to create a product that users find frustrating due to slow use.

Time complexity is talked about in relation to an algorithm, a collection of one or more functions.

>**Big O Notation** specifically helps you identify when an algorithm wouldn't 'scale' well, or work well with varying amounts of users, information, or other inputs.

Time complexity is classified by the nature of the function T(n). O represents the function, and (n) represents the number of elements to be acted on.

Worst-case time complexity, the longest it could possibly take with any valid input, is the most common way to express time complexity.

>no matter how big and fast your computer is, if the algorithm is ***exponentially inefficient***, it's realistically unusable.

When you discuss Big-O notation, that is generally referring to the worst case scenario.

For example, if we have to search two lists for common entries, we will calculate as if both entries would be at the very end of each list, just to be safe that we don't underestimate how long it could take. Sample of Big O Notations:

`O(1)` - determining if a number is odd or even. `O(1)` is a static amount of time – the same no matter how much information is there or how many users there are.

`O(log N)` - finding a word in the dictionary (using binary search). Binary search is an example of a type of 'divide and conquer' algorithm.

`O(N)` - directly and linearly connect with entry _n_. Very straight forward, ie. reading a book.

`O(N log N)` - sorting a deck of playing cards (using merge sort)

`O(N^2)` - checking if you have everything on your shopping list in your cart

`O(infinity)` - tossing a coin until it lands on heads

>As a rule of thumb, anything with N^2 or any other exponent is NOT a good algorithm for a site with multiple users.

If your algorithm slows down exponentially with the input, you're going to want to look for a more efficient way to solve that problem.

Whenever you’re coding loops within loops, you want to be especially mindful of time complexity.

Big O Cheat Sheet is the place to look once you can classify your algorithm, like as a 'merge-sort' or a 'quick-sort'.

bigocheatsheet.com/

Princeton Coursera course is NOT for the faint of heart. With examples and practice in Java, this course will cover iterating over data specifically with Java, sorting, and searching algorithms.

coursera.org/course/algs4partI

---

Q: All algorithms can be broken down to complete in a static amount of time if you do it effectively.

A: Not all algorithms can be simplified to that extent, but you should always try to find the simplest way to solve your problem.

<a id="1">1</a>: Algorithm could be one function or a set of functions that solve a problem.