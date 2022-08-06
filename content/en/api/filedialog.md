---
title: "FileDialog"
weight: 1
---

FileDialog open system file manager and show or pick files or save file

### Useage

1. Browse folder or files
```go
// open a file manager and show folder "/your/folder/path"
nux.ViewFileDialog().
    SetDirectory("/your/folder/path").
    Show()

// open a file manager and select files "logo.png" and "README.md"
nux.ViewFileDialog().
    SetActiveFileNames([]string{
        "/your/folder/path/logo.png",
        "/your/folder/path/README.md"}).
    Show()
```

2. Pick folder or files

```go
// pick files
nux.PickFileDialog().
    SetDirectory("/your/folder/path").    // default folder for first open, can be empty
    SetExtensionFilters(map[string][]string{
        "images": {"bmp","jpg", "jpeg", "png"},
        "text": {"txt"}}).
    AllowsChooseFiles().
    AllowsMultipleSelection().   // if need pick single file, do not call it
    ShowModal(func(ok bool, ret []string){
        fmt.Println(ret) // show files user picked
    })

// pick folders
nux.PickFileDialog().
    SetDirectory("/your/folder/path").
    AllowsChooseFolders().
    AllowsMultipleSelection().
    ShowModal(func(ok bool, ret []string){
        fmt.Println(ret) // show folders user picked
    })
```

3. Save a file

```go
nux.SaveFileDialog().
    SetDirectory("/your/folder/path").
    SetSaveName("save_name.png").
    ShowModal(func(ok bool, ret string){
        saveFile(ret)  // save your file
    })
```

### ViewFileDialog
| Function                | Arguments                          | Return          |
| :------------           |:--------------                     |:--              |
| SetDirectory            | (string)                           | *viewFileDialog |
| SetActiveFileNames      | ([]string)                         | *viewFileDialog |
| Show                    | ()                                 | void            |
          
### PickFileDialog          
| Function                | Arguments                          | Return          |
| :------------           |:--------------                     |:--              |
| SetDirectory            | (string)                           | *pickFileDialog |
| SetExtensionFilters     | (map[string][]string)              | *pickFileDialog |
| AllowsMultipleSelection | ()                                 | *pickFileDialog |
| AllowsChooseFiles       | ()                                 | *pickFileDialog |
| AllowsChooseFolders     | ()                                 | *pickFileDialog |
| AllowsCreateFolders     | ()                                 | *pickFileDialog |
| ShowModal               | (func(ok bool, results []string))  | void            |

### SaveFileDialog
| Function                | Arguments                          | Return          |
| :------------           |:--------------                     |:--              |
| SetDirectory            | (string)                           | *saveFileDialog |
| SetSaveName             | (string)                           | *saveFileDialog |
| ShowModal               | (func(ok bool, result string))     | void            |
