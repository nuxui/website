---
title: "Theme"
weight: 4
---


style is a **[Attr]({{< ref "/api/attr" >}})** string
```yaml
{
    import: {
        ui: nuxui.org/nuxui/ui,
    },

    style: {
        btn: {
            type: ui.Button,
            textSize: 14,
            padding: {left: 16px, top: 8px, right: 16px, bottom: 8px},
        },
        btn_default: {
            textColor: #262626,
            background: {
                type: ui.ShapeDrawable,
                states:[
                    {state:"default", shape:{
                        shape: rect,
                        solid: #e0e0e0,
                        cornerRadius: 4px,
                        shadow:{color: #88000000, x: 0, y: 1px, blur: 3px},
                    }},
                    {state:"pressed", shape:{
                        shape: rect,
                        solid: #9e9e9e,
                        cornerRadius: 4px,
                        shadow:{color: #88000000, x: 0, y: 1px, blur: 3px},
                    }},
                ]
            }
        },
    },
}

```