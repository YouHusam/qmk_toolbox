# QMK Toolbox

[![Build Status](https://github.com/qmk/qmk_toolbox/workflows/CI/badge.svg?branch=master)](https://github.com/qmk/qmk_toolbox/actions?query=workflow%3ACI)
[![Current Version](https://img.shields.io/github/tag/qmk/qmk_toolbox.svg)](https://github.com/qmk/qmk_toolbox/tags)
[![Discord](https://img.shields.io/discord/440868230475677696.svg)](https://discord.gg/Uq7gcHh)
[![License](https://img.shields.io/github/license/qmk/qmk_toolbox)](https://github.com/qmk/qmk_toolbox/blob/master/LICENSE.md)
[![GitHub contributors](https://img.shields.io/github/contributors/qmk/qmk_toolbox.svg)](https://github.com/qmk/qmk_toolbox/pulse/monthly)
[![GitHub forks](https://img.shields.io/github/forks/qmk/qmk_toolbox.svg?style=social&label=Fork)](https://github.com/qmk/qmk_toolbox/)

This is a collection of flashing tools packaged into one app. It supports auto-detection and auto-flashing of firmware to keyboards.

|Windows|macOS|
|-------|-----|
|[![Windows](https://i.imgur.com/sdh8byj.png)](https://i.imgur.com/sdh8byj.png)|[![macOS](https://i.imgur.com/3x8Xrkv.png)](https://i.imgur.com/3x8Xrkv.png)|

## Flashing

QMK Toolbox supports the following bootloaders:

 - ARM DFU (APM32, Kiibohd, STM32, STM32duino) via [dfu-util](http://dfu-util.sourceforge.net/)
 - Atmel/LUFA/QMK DFU via [dfu-programmer](http://dfu-programmer.github.io/)
 - Atmel SAM-BA (Massdrop) via [Massdrop Loader](https://github.com/massdrop/mdloader)
 - BootloadHID (Atmel, PS2AVRGB) via [bootloadHID](https://www.obdev.at/products/vusb/bootloadhid.html)
 - Caterina (Arduino, Pro Micro) via [avrdude](http://nongnu.org/avrdude/)
 - HalfKay (Teensy, Ergodox EZ) via [Teensy Loader](https://pjrc.com/teensy/loader_cli.html)
 - LUFA/QMK HID via [hid_bootloader_cli](https://github.com/abcminiuser/lufa)
 - WB32 DFU (WB32) via [wb32-dfu-updater_cli](https://github.com/WestberryTech/wb32-dfu-updater)
 - SN32 DFU (SN32) via [sonixflasher](https://github.com/SonixQMK/SonixFlasherC)
 - LUFA Mass Storage

And the following ISP flashers:

 - AVRISP (Arduino ISP)
 - USBasp (AVR ISP)
 - USBTiny (AVR Pocket)

If there's an interest in any others, they can be added if their commands are known.

## HID Console

The Toolbox also listens to HID messages on usage page `0xFF31` and usage `0x0074`, compatible with PJRC's [`hid_listen`](https://www.pjrc.com/teensy/hid_listen.html).

If you have `CONSOLE_ENABLE = yes` in your keyboard's `rules.mk`, you can print messages with `xprintf()`, useful for debugging:

![Hello world from Console](https://i.imgur.com/qxLb2zS.png)

See the [QMK Docs](https://docs.qmk.fm/#/newbs_testing_debugging?id=debugging) for more information.

## Installation

### System Requirements

* macOS 10.15 (Catalina) or higher
* Windows 10 May 2019 Update or higher (earlier with [.NET Framework 4.8](https://docs.microsoft.com/en-us/dotnet/framework/migration-guide/versions-and-dependencies#net-framework-48))

### Dependencies

When using the QMK Toolbox on Windows, it will prompt at first run to install the necessary drivers.

If you run into any issues with "Device not found" when flashing, then you may need to use [Zadig](https://docs.qmk.fm/#/driver_installation_zadig) to fix the issue.

### Download

Get the latest release [here](https://github.com/qmk/qmk_toolbox/releases).

For Homebrew users, it is also available as a Cask:

```sh
$ brew tap homebrew/cask-drivers
$ brew install --cask qmk-toolbox
```
