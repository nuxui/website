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

modify `go.mode` file, add `nuxui` dependencies

```
module example.com/my/hello

go 1.18

require nuxui.org/nuxui v0.0.1

replace nuxui.org/nuxui v0.0.1 => github.com/nuxui/nuxui v0.0.1
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

type Home interface {
	nux.Component
}

type home struct {
	*nux.ComponentBase
	content nux.Widget
}

func NewHome(attr nux.Attr) Home {
	me := &home{}
	me.ComponentBase = nux.NewComponentBase(me, attr)
	me.content = nux.InflateLayout(me, me.template())
	return me
}

func (me *home) template() string {
	return `
{
  import: {
    ui: nuxui.org/nuxui/ui,
  },

  layout: {
	widget: ui.Column,
	width: 100%,
	height: 100%,
	background: #303030,
	children:[
		{
			widget: ui.Text,
			text: Hello NuxUI,
			textSize: 30,
		}
	]
  }
}
  `
}

func init() {
	nux.RegisterWidget((*Home)(nil), func(attr nux.Attr) nux.Widget { return NewHome(attr) })
}

const manifest = `
{
  import: {
	main: main,
  }, 

  manifest: {
	  main: main.Home,
  },
}
`

func main() {
	nux.Init(manifest)
	nux.Run()
}
```

build and run hello

```shell
go build . && ./hello
```
result screenshot

<img src="/samples/screenshot_hello.jpg" width="250px" >