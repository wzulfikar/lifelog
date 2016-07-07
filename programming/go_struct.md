# Go Struct

> A struct is a collection of fields. Struct fields are accessed using a dot. (Docs)

```go
package main

import "fmt"

type Person struct {
  sex string
  age int
}

func main() {
  me := Person{"Male", 22}
  fmt.Printf("I'm %d years old %s", me.age, me.sex)
}
```

