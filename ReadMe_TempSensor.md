# Introduction #

Tempsensor utility is a small application which goal is just to show the current temperature and humidity readings from the Lascar EL-USB-RT usb sensor. The data can be further used in different applications by simply calling the application from different scripts.

## Requirements ##

  * An Lascar EL-USB-RT USB device
  * libusb-1.0 installed (see installation instructions how)

## Usage ##

Command line options;

|-s|Print only values, in format: temperature, humidity|
|:-|:--------------------------------------------------|
|-v|verbose printout                                   |
|-h|Help                                               |

If no command options are given the Tempsensor will printout temperature and humidity with text and unit symbols:

```
$ ./tempsensor 
Temperature: 24.5C, Humidity: 22%
$
```

### Only values (-s) ###

If used from script and only the values is wanted, then the -s switch should be used. It will print both temperature and humidity without any other details. These will be printed out on one line and comma separated.

Example;
```
$ ./tempsensor -s
24.5,22
$
```

### Verbose printout (-v) ###

The verbose printout, can be useful in troubleshooting situations, as it will give lot of state printouts. It works in both "-s" mode as in the normal.

Example;
```
$ ./tempsensor -v
TempSensor 0.1
Init sensor
USB Device ready
Read device
Data received:
Temperature
Data1: ffffffce
Data2: 08
Value: 24.4C
Release interface
Data received:
Humidity
Data1: 31
Value: 22%
Release interface
Temperature: 24.4C, Humidity: 22%
$
```

## Domoticz ##

To send the temp/hum data to Domoticz, then check the [Domoticz](Domoticz.md) page.

## Graphite ##

Soon...


---

## Thanks ##

Jan Axelson (for the excellent libusb example)


---

## Notes ##

Lascar EL-USB-RT is a product of Lascar Electronics Ltd.


---

## Other ##

Other open source projects that supports Lascar EL-USB-RT device;

  * http://code.google.com/p/lascar-usb-termometer/
  * https://github.com/rca/lascar-usb-thermometer


---

## Copyright ##

Copyright (C) 2013 Sebastian Sjoholm

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.