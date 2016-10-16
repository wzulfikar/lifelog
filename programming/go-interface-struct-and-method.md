# Go Interface, Struct & Method

```go
package main

import "fmt"

func main() { 
    ford := Car{} 
    ford.color = "black" 
    ford.move(40) 
    ford.stop()
}

type Vehicle interface { 
    move(speed int) stop()
}

type Car struct { 
    color string
}

func (c *Car) move(speed int) { 
    fmt.Println("the", c.color, "car is moving at", speed, "km/h")
}

func (c *Car) stop() { 
    fmt.Println("car is stopped")
}
```