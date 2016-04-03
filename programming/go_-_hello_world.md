# GO - Hello World!

```go
package main

import (
	"fmt"
	"runtime"
	"time"
	"log"
)

func main() {
	defer executionTimer(time.Now(), "HelloWorld")

	fmt.Println("Hello world from", runtime.GOOS)
}

func executionTimer(start time.Time, name string) {
  fmt.Println()
  log.Printf("➜ ❝%s❞ took %s to execute.", name, time.Since(start))
}
```
