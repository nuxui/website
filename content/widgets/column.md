---
title: "Column"
weight: 1
---

A widget that displays its children in a vertical array.  
[Full example](https://github.com/nuxui/samples/tree/master/widgets/column)

```yaml
layout: {
    widget: ui.Column,
    width: 100px,
    height: 100px,
    background: #303030,
    children:[
        {
            widget: ui.Text,
            width: 100%,
            text: top text,
            background: #ff0000,
        },{
            widget: ui.Text,
            height: 1wt,
            text: bottom text,
            background: #ff00ff,
        },
    ]
}
```

![](https://raw.githubusercontent.com/nuxui/samples/master/widgets/column/preview.jpg)