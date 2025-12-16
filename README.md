# Glasnost M9G10 - Open Hardware Linux SBC

An open hardware and software Single Board Computer based on the Microchip AT91SAM9G10, designed for IoT and embedded applications with full SPI/UART/I2C expansion capabilities. This is a learning project exploring Linux board design with mainline kernel support.

![board_render](/docs/assets/front.png)


### Features

| Characteristic | Description |
| --- | --- |
| Dimensions | 66mm x 42mm |
| Processor | AT91SAM9G10 - ARM926EJ @ 266MHz |
| Oscillators |  18.432MHz main clock, 32.768kHz RTC |
| RAM | SDRAM 1Gb max (2x 512Mbit modules) |
| Storage | microSD |
| USB | 1 microUSB Host/Client, 2 USB host |
| Ethernet | N/A |
| WiFi/BT | WiFi module onboard |
| Supply | USB, 5V max |
| Interfaces | SPI, UART, I2C, GPIO exposed on headers |
| OS Support | Linux (mainline kernel with custom device tree) |

Common interfaces such as I2C, SPI, UART and GPIO are exposed on the header.

### ⚠️ Boot Note

> **Unlike other Glasnost boards**, this SBC does **not** include NOR Flash for a recovery environment. The AT91SAM9G10's limited peripheral availability means the board relies entirely on microSD card boot. Linux must be booted from the microSD card—there is no fallback recovery distro on internal flash.


### Tools & Design

This project is created using **KiCad 9**

### Documentation & Resources

Complete documentation including schematics, PCB design, and build instructions is available in the [docs](docs/) directory and published at the project website.

For pre-built artifacts:
   - [Fabrication files and releases](https://github.com/vd-rd/sbc_at91sam9g10/releases)

### Status & Licensing

- **Status**: Stable
- **License**: Open Hardware (not officially certified, community design)
- **Open Source**: All hardware designs and software are open source

### References & Inspiration

- [AT91SAM9G10 Datasheet](resources/Atmel-6062-ARM926EJ-S-Microprocessor-SAM9261_Datasheet.pdf)
- [AT91SAM9G10EK Evaluation Kit](https://www.microchip.com/)
- [AT91Bootstrap](https://github.com/linux4sam/at91bootstrap)
