# BusyBridge

BusyBridge is an open-source ESP32-S2-based USB HID emulator that enables a Yealink BLT60 to operate as a Kuando-compatible Busylight.

The goal of this project is to reuse the inexpensive and widely available Yealink BLT60 as a drop-in replacement for an original Kuando Busylight by emulating the required USB HID protocol on an ESP32-S2.

The project allows a Yealink BLT60 status light to be used with software that supports the original Kuando device, including AGFEO Dashboard and Kuando HUB.

## Features

- Emulates an original Kuando Busylight USB HID device
- Compatible with ESP32-S2
- Drives a Yealink BLT60 over its 2.5 mm connector
- Supports RGB colors
- Supports blinking status indications
- Supports status changes from host software
- Successfully tested with:
  - AGFEO Dashboard
  - Kuando HUB
- Open source

## Hardware

### Tested Hardware

- ESP32-S2 Mini
- Yealink BLT60

### BL
