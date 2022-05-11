---
title: "Button"
weight: 1
---


```yaml
layout: {
    widget: ui.Column,
    width: auto,
    height: 100px,
    background: #eae5ec,
    padding: 10px,
    children:[
        {
            widget: ui.Button,
            text: normal button,
        },{
            widget: ui.Button,
            text: icon button,
            margin:{top: 10px},
            icon:{
                left: {
                    widget: ui.Image,
                    width: 1em,
                    height: 1em,
                    margin:{right: 3px },
                    src: "delete.png",
                },
            },
        }
    ]
}
```

![](https://raw.githubusercontent.com/nuxui/samples/master/widgets/button/preview.jpg)