# Getting started

This page takes you from a board on your desk to boot messages on your screen. It assumes you've used a terminal before, but not that you've brought up a Linux board from scratch.

## What you need

| Item | Notes |
|---|---|
| Glasnost M9G10 board | |
| microSD card, **2 GB or smaller** | The processor can only boot from standard-capacity (SDSC) cards — see [Boot & recovery](hardware-ref/boot.md). |
| 5 V USB-C power supply | 1 A or more is recommended: WiFi transmit bursts draw much more than idle. |
| USB-to-serial adapter, **3.3 V** | For the [debug console](#2-connect-the-debug-console). A 5 V adapter can damage the board. |
| Jumper wires | Three female–female wires for the adapter. |
| A computer with a terminal program | e.g. `picocom`, `minicom`, PuTTY. |

## 1. Prepare the microSD card

!!! note "Ready-made images"
    Prebuilt images are not published yet. Until then, build the bootloaders and Linux yourself — see [Software](software-ref/index.md).

1. Format the card as **FAT** (FAT16 or FAT32).
2. Copy the first-stage bootloader to the root of the card as **`boot.bin`**. The processor looks for exactly this file name.
3. Copy the rest of the image (U-Boot, kernel, device tree, root filesystem) as described in [Software](software-ref/index.md).

## 2. Connect the debug console

The debug console is a serial port that shows every boot message and later gives you a login prompt. It's on the [main header (J4)](hardware-ref/connectors.md#main-header-j4):

| Adapter | Board (J4) |
|---|---|
| GND | pin 14 (GND) |
| RX | pin 11 (debug console TX) |
| TX | pin 12 (debug console RX) |

Don't connect the adapter's power pin. Open your terminal program at **115200 baud, 8N1**, no flow control. For example:

```sh
picocom -b 115200 /dev/ttyUSB0
```

## 3. Power up

1. Insert the microSD card.
2. Plug in the USB-C power supply.

You should see, in order: the bootloader (AT91Bootstrap) messages, then U-Boot, then the Linux kernel starting.

!!! note
    The exact expected output for revision 2.0 hasn't been documented yet.

## If nothing appears

- Check the adapter wiring: TX and RX are crossed (adapter TX → board RX).
- Check the card is 2 GB or smaller, FAT-formatted, with `boot.bin` in the root.
- With no bootable card, the processor starts its recovery mode (SAM-BA) and waits for a computer on the USB-C port or the debug console — see [Boot & recovery](hardware-ref/boot.md).
- Check [known issues](hardware-ref/known-issues.md).

## Next steps

- [Connectors & pinout](hardware-ref/connectors.md) — what's on the header.
- [Software](software-ref/index.md) — build your own image.
