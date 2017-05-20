# notes from go package video:

https://www.youtube.com/watch?v=CF9S4QZuV30

- 01.00
- 02.21
- 04.35
- 08.15
- 08.40
- 15.24: slice
- 17.25: slice with defined value
- 18.39: map
- 19.43: delete map by key
- 23.17: variadic function
- 24.40: closure
- 25.30: recursion
- 28.00: defer function
- 29.00: safe division with recover
- 30.28: panic
- 31.30: intro to pointer
- 33.00: print memory address of a variable
- 33.16: generate pointer with "new"
- 33.50: golang struct
- 35.00: assigning method to struct (function that belongs to struct)
- 36.00-38.30: interface
- 40.50: golang built-in split function
- 41.37: file io
- 43.24: type conversion
- 44.40: creating http server with built-in net/http
- 47.20: go routine
- 49.25: go channel
- 50.27: send data to next routine via go channel
- 51.09: receiving data from channel
- 


- use `strconv.Itoa` to convert int to string
- initializing type can be by order or by colon notation
- pointer is basically passing memory address and assigning value in there
- golang pass value by default
- statically typed = can't change
- go clauses have no bracket
- no need for break in go's switch
- slice is like array, but you don't need to define the size
- channel: pass data between go routines

---
codeforce golang:
- unlike when codes put in main, when in function, exec time is less but memory is more
- using if else cost more than using unchained if
