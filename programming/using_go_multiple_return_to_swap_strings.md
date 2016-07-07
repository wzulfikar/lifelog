# Using Go Multiple Return to Swap Strings

>A function can return any number of results. (Go Docs)

```go
package main

import (
  "fmt"
)

func main() {
    // declare vars
	a, b := "4", "5"
	fmt.Println("before swap:", a, b)
    
    // swap vars
	a, b = swap(a, b)
	fmt.Println("after swap:", a, b)
}

func swap(a, b string) (string, string) {
  // return 2 strings
  return b, a
}
```