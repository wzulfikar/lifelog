# Detecting OS Using Built-in Function

> A case body breaks automatically, unless it ends with a fallthrough statement. (Docs)

```go
package main

import (
  "fmt"
  "runtime"
)

func main() {
  fmt.Println("Go runs on", detectOs())
}

func detectOs() string {
  // freebsd, openbsd,
  // plan9, windows...
  os := runtime.GOOS

  switch os {
    case "darwin":
      os = "OS X"
    case "linux":
      os = "Linux"
  }

  return os
}

```

