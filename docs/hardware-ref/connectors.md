# Connectors & pinout

Every connector on the board and what each pin does. All signals are **3.3 V** — none of them tolerate 5 V.

## Main header (J4)

2×18 pins, 2.54 mm pitch, mounted on the **bottom** side of the board. The pin numbering follows the shared Glasnost header layout, so capes fit every Glasnost board.

| Pin | Signal | Processor pin | Notes |
|---|---|---|---|
| 1 | GND | | |
| 2 | 3.3 V | | Output from the board's regulator |
| 3–6 | — | | Not connected on this board |
| 7 | RESET | NRST | Active low; pull low to reset the board |
| 8–10 | — | | Not connected on this board |
| 11 | Debug console TX | PA10 (DTXD) | Board transmits; 115200 baud |
| 12 | Debug console RX | PA9 (DRXD) | Board receives |
| 13 | GPIO1 | PA14 | |
| 14 | GND | | |
| 15 | UART1 TX | PC12 (TXD1) | |
| 16 | UART1 RX | PC13 (RXD1) | |
| 17 | I²C SCL | PA8 (TWCK) | No pull-up on the board — see [known issues](known-issues.md) |
| 18 | I²C SDA | PA7 (TWD) | No pull-up on the board |
| 19 | GPIO3 | PC0 | Driven by the processor during boot — see [known issues](known-issues.md) |
| 20 | GPIO2 | PA15 | |
| 21 | UART2 TX | PC14 (TXD2) | |
| 22 | UART2 RX | PC15 (RXD2) | |
| 23 | GND | | |
| 24 | GPIO4 | PC3 | Driven as an address line from reset — see [known issues](known-issues.md) |
| 25 | SPI SCK | PB29 (SPI1) | Shared with the on-board DataFlash |
| 26 | SPI CS | PB28 (SPI1 NPCS0) | |
| 27 | SPI MOSI | PB31 | Shared with the on-board DataFlash |
| 28 | SPI MISO | PB30 | Shared with the on-board DataFlash |
| 29–30 | (CAN TX/RX) | | Not connected on this board (shared layout) |
| 31–35 | (GPIOA1–5) | | Not connected on this board (shared layout) |
| 36 | GND | | |

!!! note
    There is **no 5 V pin** on this board's header, and no power input: the board is powered only through the USB-C port.

## USB host header (J3)

2×4 pins, 1.27 mm pitch. Carries one USB host port for a cape. **There is no 5 V (VBUS) on this header** — the cape must make its own 5 V for USB devices.

| Pin | Signal |
|---|---|
| 1, 7 | GND |
| 2–5 | Not connected |
| 6 | USB D+ |
| 8 | USB D− |

## USB-C (J5)

Power input (5 V) and USB 2.0 full-speed **device** port — the board can't act as a USB host here. Also used for recovery mode (SAM-BA), see [Boot & recovery](boot.md).

## microSD slot (J1)

Push-push slot. The card-detect switch reads **high when a card is inserted** (processor pin PA11).

## Antenna (AE1)

U.FL connector for the WiFi antenna.

## LED and buttons

| Part | Processor pin | Notes |
|---|---|---|
| RGB LED red | PA29 | Active low |
| RGB LED green | PA28 | Active low |
| RGB LED blue | PA26 | Active low |
| SW1 (user button) | PB25 | Reads low when pressed |
| SW2 (wake-up) | WKUP | Wakes the processor from shutdown |
