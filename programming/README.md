# Programming

Most of the stuff here is basically my personal approach, which might not be best practice for you. Sometimes it just code snippets. 

Anyway, I'm open to any idea, suggestion or comment 😉

https://www.vividcortex.com/blog/2014/01/15/two-go-memory-leaks/

https://blog.rubylearning.com/best-practices-for-a-new-go-developer-8660384302fc#.q3yzzxiur

https://talks.golang.org/2013/bestpractices.slide#2

http://talks.golang.org/2014/go4gophers.slide#6

http://talks.golang.org/2012/splash.article

in golang, interface is instantiable

tour about interface: https://tour.golang.org/methods/10

```go
// from https://tour.golang.org/methods/10
package main

import "fmt"

type I interface {
	M()
}

type T struct {
	S string
}

// This method means type T implements the interface I,
// but we don't need to explicitly declare that it does so.
func (t T) M() {
	fmt.Println(t.S)
}

func main() {
	var i I = T{"hello"}
	i.M()
}
```