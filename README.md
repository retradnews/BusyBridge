# BusyBridge

BusyBridge is an open-source ESP32-S2 based emulator for the Kuando Busylight.

The project allows a Yealink BLT60 status light to be used as a Kuando-compatible Busylight with software that supports the original Kuando device, including AGFEO Dashboard and Kuando HUB.

## Features

- Emulates an original Kuando Busylight USB HID device
- Compatible with ESP32-S2
- Drives a Yealink BLT60 over its 2.5 mm connector
- Supports RGB colors
- Supports status changes from host software
- Successfully tested with:
  - AGFEO Dashboard
  - Kuando HUB
- Open source

## Hardware

### Tested Hardware

- ESP32-S2 Mini
- Yealink BLT60

### BLT60 Wiring

| BLT60 Contact | Function/LED Color | ESP32 GPIO |
|--------------|----------|------------|
| Sleeve | Common Anode / 3.3 V | 3V3 |
| Tip | Red | GPIO18 |
| Ring1 | Green | GPIO17 |
| Ring2 | Blue | GPIO16 |

## How it Works

BusyBridge emulates the USB descriptors and HID reports of an original Kuando Busylight. To the host PC it appears as a genuine Kuando device, while translating received color and status commands into LED control signals for the attached BLT60.

## Status

Current project status:

- USB enumeration working
- HID communication working
- Identity responses implemented
- Color control working
- AGFEO Dashboard compatible
- Kuando HUB compatible

Blink mode support is currently under validation.

## Building

Developed using:

- Arduino IDE
- ESP32 Arduino Core
- ESP32-S2 USB HID

Compile and flash the firmware to an ESP32-S2 board.

## Technical Notes

The Yealink BLT60 itself is a very simple device.

A teardown and electrical analysis showed that the BLT60 contains only two RGB LEDs connected in parallel. No microcontroller, USB interface, sound generator, or any other active electronics are present inside the unit.

All color control is performed externally through the four-wire connection:

- Common Anode (+3.3 V)
- Red LED channel
- Green LED channel
- Blue LED channel

Because of this simple design, the BLT60 cannot reproduce certain features of the original Kuando Busylight hardware.

### Limitations Compared to an Original Kuando Busylight

- No acoustic signaling (buzzer)
- No sound notifications
- No internal USB electronics
- No onboard controller

Visual status indication through RGB LEDs is fully supported. Features that rely on an integrated buzzer are not available on the BLT60 hardware.

## License

MIT License

Copyright (c) 2026 Swen Langel

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software.

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

## Disclaimer

This project is not affiliated with, endorsed by, or sponsored by PLENOM, Kuando, Yealink, or AGFEO.

All trademarks belong to their respective owners.
