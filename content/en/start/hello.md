---
title: "Write your first app"
weight: 1
---

create `hello` project
``` shell
mkdir hello
cd hello
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

then update dependencies

```shell
go mod init example.com/hello
go mod tidy
```

build and run hello

```shell
go build . && ./hello
```
result screenshot

<img src="/samples/screenshot_hello.webp" width="250px" >