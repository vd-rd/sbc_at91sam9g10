# Hardware overview

What's on the board, in one place. Details for each part are on the pages linked below.

## Specifications

| | |
|---|---|
| Processor | Microchip AT91SAM9G10 — ARM926EJ-S core at 266 MHz, 217-ball BGA |
| Memory | 64 MB SDRAM (2× MT48LC16M16A2, 256 Mbit each, 32-bit bus) by default; up to 128 MB with 2× 512 Mbit chips (MT48LC32M16) |
| Storage | microSD card slot (boot and root filesystem); 2 MB SPI DataFlash (AT45DB161D, data only — the boot ROM can't boot from it) |
| USB | USB-C port: power in, USB 2.0 full-speed device, recovery. One USB host port on header J3 for a cape. A second USB host port is used by the on-board WiFi. |
| Wireless | WiFi module (RTL8188CUS) with U.FL antenna connector; a WiFi/Bluetooth combo module with the same pinout also fits |
| Expansion | [Main header J4](connectors.md#main-header-j4), 2×18 pins, 2.54 mm: debug console, 2 UARTs, I²C, SPI, 4 GPIO, reset, 3.3 V |
| User interface | RGB status LED, one user button, one wake-up button |
| Clocks | 18.432 MHz main crystal, 32.768 kHz crystal for the real-time clock |
| Power | 5 V through the USB-C port; on-board 3.3 V and 1.2 V regulators — see [Power](power.md) |
| PCB | 4 layers, 66 × 42 mm — see [PCB](pcb.md) |

## What's on the board

| Ref | Part | Function |
|---|---|---|
| U1 | AT91SAM9G10 | Processor |
| U2, U3 | MT48LC16M16A2 | SDRAM |
| U5 | AT45DB161D | SPI DataFlash (data storage) |
| U6 | RTL8188CUS module | WiFi |
| U7, U8 | TPS62A01A | 3.3 V and 1.2 V regulators |
| J1 | microSD slot | Boot media |
| J3 | 2×4 header, 1.27 mm | USB host port for a cape |
| J4 | 2×18 header, 2.54 mm | Main header (mounted on the bottom side) |
| J5 | USB-C | Power and USB device |
| AE1 | U.FL | WiFi antenna |
| D3 | RGB LED | Status |
| SW1, SW2 | Buttons | User button, wake-up button |
| TP4–TP6 | Test points | 5 V input, 1.2 V core, 3.3 V |

## More

- [Connectors & pinout](connectors.md)
- [Power](power.md)
- [Boot & recovery](boot.md)
- [Schematics](schematics.md), [PCB](pcb.md), [BOM](bom.md)
- [Build your own](build-your-own.md)
- [Known issues](known-issues.md)
- Datasheets: [processor](https://github.com/vd-rd/sbc_at91sam9g10/blob/main/resources/datasheet-at91sam9g10-doc6462B.pdf), and the [full list](https://github.com/vd-rd/sbc_at91sam9g10/blob/main/resources/REFERENCES.md)
