---
title: "Android Installation"
weight: 4
GeekdocHidden: true
---

## System requirements

To install and run NuxUI, your development environment must meet these minimum requirements:

1. **Golang 1.8+** 

Download and install Golang： [golang installation instructions](https://go.dev/doc/install)

2. **Android NDK**

Download Android Studio https://developer.android.com/studio
Download Android NDK https://developer.android.com/ndk/downloads

Set Environment<br>
`ANDROID_HOME`: /your/android/sdk/home<br>
`ANDROID_NDK_HOME`: /your/android/ndk/home<br>

## Build Android Application

Install build tool
```
go install nuxui.org/nuxui/cmd/nux@latest
```

Build for Android
```
# build all architecture
nux build -target=android .

# only build for arm
nux build -target=android/arm .

# build for arm and optimiz size
nux build -target=android/arm -ldflags="-s -w" . 
```

Install app to devices
```
adb install -r app.apk
```

Example

```
cd github.com/nuxui/samples/counter
nux build -target=android/arm -ldflags="-s -w" . 
adb install -r counter.apk
```

Preview

<img src="/samples/screenshot_android.webp" width="400px" >
