---
title: "Color"
weight: 1
---

Color is a RGBA color same with html css
```
type Color uint32
```

Consts of colors

```go
const (
    Transparent Color = 0x00000000
    White       Color = 0xFFFFFFFF
    Black       Color = 0x000000FF
    Red         Color = 0xFF0000FF
    Green       Color = 0x00FF00FF
    Blue        Color = 0x0000FFFF
    Purple      Color = 0xFF00FFFF
    Yellow      Color = 0xFFFF00FF
)
```

### Useage

```go
c1, err := nux.ParseColor("#ff0000", nux.Transparent) // c1 is 0xFF0000FF
c1, err := nux.ParseColor("ff0000", nux.Transparent) // c1 is Transparent, err is not nil
var c2 nux.Color = 0xFF0000FF
```



### Functions
| Function                | Arguments                          | Return             |
| :------------           |:--------------                     |:--                 |
| RGBAf                   | ()                                 | r, g, b, a float32 |
| ARGB                    | ()                                 | uint32             |
| Equal                   | (Color)                            | bool               |
          