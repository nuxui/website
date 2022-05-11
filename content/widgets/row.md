---
title: "Row"
weight: 1
---

A widget that displays its children in a horizontal array
[Full example](https://github.com/nuxui/samples/tree/master/widgets/row)

```yaml
layout: {
    widget: ui.Row,
    width: 200px,
    height: 200px,
    background: #303030,
    children:[
        {
            widget: ui.Text,
            width: 1wt,
            text: left text,
            background: #ff0000,
        },{
            widget: ui.Text,
            height: 100%,
            text: right text,
            background: #ff00ff,
        },
    ]
}

```

![](https://raw.githubusercontent.com/nuxui/samples/master/widgets/row/preview.jpg)
