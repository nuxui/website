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

NuxUI use windows `GDI+` as default graphic render backend library, It means NuxUI can run directly without any third part graphic library 


NuxUI also support `cairo` as graphic render backend library. To use `cairo` graphic library, your development environment must meet these minimum requirements:

[**msys2**](https://www.msys2.org/) lastest version

Download and initialization msys2 by follow official website instructions

Install cairo dependens for 32bit golang. 
```
pacman -S  mingw-w64-i686-cairo mingw-w64-i686-pango mingw-w64-i686-libjpeg-turbo
```

Install cairo dependens for 64bit golang. 
```
pacman -S mingw-w64-x86_64-cairo mingw-w64-x86_64-pango mingw-w64-x86_64libjpeg-turbo
```

After everything prepared, try to build [`hello`](https://github.com/nuxui/samples) in samples code