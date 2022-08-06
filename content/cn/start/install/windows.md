---
title: "Windows 安装"
weight: 1
GeekdocHidden: true
next:
  title: Set up an editor
  path: /get-started/editor
---

## 系统需要

To install and run NuxUI, your development environment must meet these minimum requirements:

1. **golang 1.8+** 

下载并安装 golang： [golang installation instructions](https://go.dev/doc/install)

只需要 golang 就可以编译例子 [`hello`](https://github.com/nuxui/samples)，命令如下：
```shell
go build .
```

 2. **Cairo** (可选的)

NuxUI 默认使用 `GDI+` 来渲染界面，这意味着只需要 golang 就可以直接创建或运行 NuxUI 应用

NuxUI 也支持使用 [`cairo`](https://www.cairographics.org/) 来渲染界面. To use `cairo` graphic library, your development environment must meet these minimum requirements:

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