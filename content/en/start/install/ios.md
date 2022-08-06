---
title: "IOS install"
weight: 4
GeekdocHidden: true
---

## System requirements

To install and run NuxUI, your development environment must meet these minimum requirements:

**1. golang 1.8+** Download and install golang 

[Dwonload golang](https://go.dev/dl/)  
[golang installation instructions](https://go.dev/doc/install)

**2. macOS Developer Tools**

```shell
xcode-select --install
```

**3. Xcode**

## Build IOS App

Install build tool
```shell
go install nuxui.org/nuxui/cmd/nux@latest
```

Build for ios
```shell
nux build -target=ios -bundleid="your.bundle.id" .
```

Build for iossimulator
```shell
nux build -target=iossimulator -bundleid="your.bundle.id" .
```

If `failed to pull the signing certificate to determine your team ID`, add teamid manual

Find any xcode project, open file `project.pbxproj` and find `DEVELOPMENT_TEAM = YOURTEAMID`, then:
```shell
nux build -target=iossimulator -bundleid="your.bundle.id" -teamid="YOURTEAMID" .
```
Install app to device
```
open -a Simulator
xcrun simctl install booted ./hello.app
```

Example
```shell
open -a Simulator

cd nuxui/samples/counter

/Users/mustodo/go/bin/nux build -target=iossimulator -bundleid="a.b" -teamid="MU53V3J3JA" .

xcrun simctl install booted ./counter.app
```

Preview

<img src="/samples/screenshot_counter.webp" width="400px" >
