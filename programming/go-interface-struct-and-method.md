# Go Interface, Struct & Method

```go
package main

import "fmt"

func main() { 
    ford := Car{} 
    ford.color = "black" 
    ford.start() 
    ford.move(40) 
    ford.stop()
}

type Vehicle interface { 
    start() 
    move(speed int) 
    stop()
}

type Car struct {
    isStarted bool 
    color string
}

// what's the diff between `func (c Car)` & `func (c *Car)`?// `func (c Car)` will pass Car by value
// while `func (c *Car)` will pass it by reference.// try change receiver of start method below from// `c *Car` to `c Car`.
func (c *Car) start() { 
    c.isStarted = true 
    fmt.Println("engine is started")
}

func (c Car) move(speed int) { 
    if !c.isStarted { 
        panic("Engine not started") 
    }         
    fmt.Println("the", c.color, "car is moving at", speed, "km/h")
}

func (c *Car) stop() { 
    c.isStarted = false fmt.Println("car is stopped")
}
// TODO: what's the diff between `func (c Car)` & `func (c *Car)`
```