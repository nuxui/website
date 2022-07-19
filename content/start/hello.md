---
title: "Write your first app"
weight: 1
---

create `hello` project
``` shell
mkdir hello
cd hello
go mod init example.com/my/hello
```

modify `go.mod` file, add `nuxui` dependencies

```
module example.com/my/hello

go 1.18

require nuxui.org/nuxui v0.0.5

replace nuxui.org/nuxui v0.0.5 => github.com/nuxui/nuxui v0.0.5
```

then update dependencies

```shell
go mod tidy
```

create a `hello.go` file and programing:

```go
package main

import (
    "nuxui.org/nuxui/nux"
    _ "nuxui.org/nuxui/ui"
)

func main() {
    nux.Run(nux.NewWindow(nux.Attr{
        "width":  "15%", // screen_width x 15%
        "height": "2:1", // width : height = 2 : 1
        "title":  "hello",
        "content": nux.Attr{
            "type": "nuxui.org/nuxui/ui.Text",
            "text": `Hello nuxui`,
        },
    }))

}
```

build and run hello

```shell
go build . && ./hello
```
result screenshot

<img src="/samples/screenshot_hello.jpg" width="250px" >