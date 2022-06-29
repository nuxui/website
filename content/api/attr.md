---
title: "Attr"
weight: 1
---

Attr is a map with string key and any value
```go
type Attr map[string]any
```
Useage:
```go
attr := nux.Attr{
    "width": 10,
    "height": "10%",
    "color": "#ff0000",
    "font": nux.Attr{
        "family": "arial",
        "size": 14,
    },
}

attr.Has("text") // false
attr.Has("width") // true
attr.GetInt32("width", 80) // 10
attr.GetDimen("height", nux.ADimen(50, nux.Pixel)) // nux.Dimen{10, nux.Percent}
attr.GetString("text", "default text") // default text
attr.GetAttr("font", nil) // nux.Attr{"family": "arial", "size": 14}
attr.GetColor("color", 0xffffff) // 0xff0000
```

| Function          | Arguments                | Return      |
| :------------     |:--------------           |:--          |
| Has               | (string)                 | bool        |
| Set               | (string, any)            | void        |
| Get               | (string, any)            | any         |
| GetAttr           | (string, nux.Attr)       | nux.Attr    |
| GetString         | (string, string)         | string      |
| GetBool           | (string, bool)           | bool        |
| GetColor          | (string, nux.Color)      | nux.Color   |
| GetDimen          | (string, nux.Dimen)      | nux.Dimen   |
| GetInt8           | (string, int8)           | int8        |
| GetInt32          | (string, int32)          | int32       |
| GetInt64          | (string, int64)          | int64       |
| GetFloat32        | (string, float32)        | float32     |
| GetFloat64        | (string, float64)        | float64     |
| GetArray          | (string, []any)          | []any       |
| GetStringArray    | (string, []string)       | []string    |
| GetAttrArray      | (string, []nux.Attr)     | []nux.Attr  |