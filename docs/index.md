---
template: home.html
title: GLASNOST M9G10
---

# Glasnost M9G10

An open hardware and software Single Board Computer based on the Microchip AT91SAM9G10, designed for IoT and embedded applications with full SPI/UART/I2C expansion capabilities.

## Overview

The Glasnost M9G10 is a learning project exploring Linux board design with mainline kernel support. It provides a compact, flexible platform for embedded applications with extensive expansion possibilities through standard interfaces.

### Key Specifications

- **Processor**: AT91SAM9G10 - ARM926EJ @ 266MHz
- **Memory**: Up to 1GB SDRAM (2x 512Mbit modules)
- **Storage**: microSD card
- **Connectivity**: WiFi module onboard, USB (1x microUSB Host/Client, 2x USB host)
- **Interfaces**: SPI, UART, I²C, GPIO exposed on headers
- **Operating System**: Linux with mainline kernel support and custom device tree
- **Size**: 66mm x 42mm

## Important Note

> Unlike other Glasnost boards, this SBC does **not** include NOR Flash for a recovery environment. The AT91SAM9G10's limited peripheral availability means the board relies entirely on microSD card boot.

## Getting Started

Ready to dive in? Check the [Getting Started](getting-started.md) guide to learn how to set up your board and load firmware.

## Documentation

This site contains complete documentation for both hardware and software:

- **[Hardware Documentation](hardware-ref/index.md)**: Schematics, PCB design, BOM, and build instructions
- **[Software Documentation](software-ref/index.md)**: Compilation guides, bootloader details, and OS configuration

## Project Status

- **Status**: Stable
- **License**: Open Hardware (community design)
- **Open Source**: All hardware designs and software are open source

## Resources

- [GitHub Repository](https://github.com/vd-rd/sbc_at91sam9g10)
- [Fabrication Files & Releases](https://github.com/vd-rd/sbc_at91sam9g10/releases)
- [AT91SAM9G10 Datasheet](../resources/Atmel-6062-ARM926EJ-S-Microprocessor-SAM9261_Datasheet.pdf)