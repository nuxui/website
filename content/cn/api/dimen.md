---
title: "Dimen"
weight: 1
---

Dimen
```
type Dimen int32
type Mode byte  // dimen mode
type MeasureDimen int32  // Non-negative and only support Pixel, Auto, Unlimit
```

Consts of colors

```go
const (
    Pixel   Mode = iota // 1 means 1px
    Auto                // wrap content
    Unlimit             // MeasureDimen used Pixel, Auto, Unlimit
    Weight              // 1wt, no negative
    Ratio               // 16:9, no zero, no negative
    Percent             // 50% means (parent.size - parent.padding)*0.5
    Ems                 // 1em = 1 x font-size
    pixel               // negative pixel 111
)
```

### Useage

```go
d1 := nux.ADimen(10, nux.Pixel)   // d1 = 10px
d2 := nux.ADimen(10, nux.Percent) // d2 = 10%
d3 := nux.ADimen(1, nux.Weight)   // d3 = 1wt
d4 := nux.ADimen(100, nux.Auto)   // d4 = auto, max = 100px

d5, err := nux.ParseDimen("10px") // d5 = 10px, err = nil
d6, err := nux.ParseDimen("10")   // d6 = 0px, err != nil
d7 := SDimen("10%")               // d7 = 10%
d8 := SDimen("2:1")               // d8 = 2:1, width/height is 2/1
d9 := SDimen(":1")                // d9 = 0px, print error
```



### Dimen Functions
| Function                | Arguments                          | Return             |
| :------------           |:--------------                     |:--                 |
| Mode                    | ()                                 | nux.Mode           |
| Value                   | ()                                 | float32            |
| String                  | ()                                 | string             |
          