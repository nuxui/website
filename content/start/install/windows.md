---
title: "Windows install"
weight: 1
GeekdocHidden: true
next:
  title: Set up an editor
  path: /get-started/editor
---

## System requirements

To install and run NuxUI, your development environment must meet these minimum requirements:

**golang 1.8+** Download and install golang 

[Dwonload golang](https://go.dev/dl/)  
[golang installation instructions](https://go.dev/doc/install)

### Use GDI+ backend

NuxUI use windows `GDI+` as default graphic render backend library, It means NuxUI can run directly without any third part graphic library 

build samples [`hello`](https://github.com/nuxui/samples) with command
```shell
go build .
```

### Use Cairo backend
NuxUI also support [`cairo`](https://www.cairographics.org/) as graphic render backend library. To use `cairo` graphic library, your development environment must meet these minimum requirements:

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