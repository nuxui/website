---
title: "Android Installation"
weight: 4
GeekdocHidden: true
---

## System requirements

To install and run NuxUI, your development environment must meet these minimum requirements:

1. **golang 1.8+** 

Download and install Golang： [golang installation instructions](https://go.dev/doc/install)

Just need Golang for build samples [`hello`](https://github.com/nuxui/samples), command is:
```shell
go build .
```

 2. **Cairo** (optional)

NuxUI use `GDI+` as default graphic render backend, it means just need golang can build and run NuxUI applications

NuxUI also supported [`cairo`](https://www.cairographics.org/) as graphic render backend. To use `cairo` graphic library, your development environment must meet these minimum requirements:

[**msys2**](https://www.msys2.org/) lastest version

Download and initialization msys2 by follow official website instructions

Install cairo dependens for golang. 
```
# 32bit
pacman -S mingw-w64-i686-cairo mingw-w64-i686-pango mingw-w64-i686-libjpeg-turbo
# 64bit
pacman -S mingw-w64-x86_64-cairo mingw-w64-x86_64-pango mingw-w64-x86_64libjpeg-turbo

```

After everything prepared, build samples [`hello`](https://github.com/nuxui/samples) with `-tags cairo` command
```shell
go build -tags cairo .
```