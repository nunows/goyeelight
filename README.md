# goyeelight
Control the Yeelight LED Bulb with Go

[![GoDoc](https://godoc.org/github.com/nunows/goyeelight?status.svg)](https://godoc.org/github.com/nunows/goyeelight)

## Usage

The "Developer Mode" need to be enabled to discover and operate the device.

### Quick Start

#### Install

``` bash

go get github.com/nunows/goyeelight

```

#### Example to control the Yeelight WiFi LED



``` go
package main

import "fmt"
import "github.com/nunows/goyeelight"

func main() {
      // new Yeelight instance
      lamp := goyeelight.New("192.168.1.255", "55443")

      var r string

      // turn on the smart LED
      r = lamp.On()
      fmt.Println(r)
      // get the "power" and "bright" propertys
      r = lamp.GetProp(`"power","bright"`)
      fmt.Println(r)
      // set the bright to 50
      lamp.SetBright("50","smooth","500")
      fmt.Println(r)
      // turn off the smart LED
      r = lamp.Off()
      fmt.Println(r)
}
```

### Methods available in the package:

* GetProp
* SetCtAbx
* SetRGB
* SetHSV
* SetBright
* SetPower
* Toogle
* SetDefault
* StartCf
* StopCf
* SetScene
* CronAdd
* CronDel
* CronGet
* SetAdjust
* SetName
* On
* Off

Note: Only tested with Yeelight LED Bulb (Color) with the firmware 1.4.1_45
