# Power

The board runs from **5 V on the USB-C port**. It has no other power input.

## Supply

- Use a 5 V USB-C supply rated **1 A or more**. A computer's USB port works for light use, but WiFi transmit bursts can exceed what a 500 mA port provides.
- The USB-C port asks for default USB power only (5.1 kΩ on CC1/CC2); it doesn't negotiate higher voltages.

## Rails

| Rail | Voltage | Made by | Feeds | Test point |
|---|---|---|---|---|
| 5 V input | 5 V | USB-C | both regulators | TP4 |
| 3.3 V | 3.3 V | U7 (TPS62A01A buck) | processor I/O, PLL and oscillator, SDRAM, microSD, WiFi, DataFlash, header pin 2 | TP6 |
| 1.2 V | 1.2 V | U8 (TPS62A01A buck) | processor core and backup domain | TP5 |

Both regulators start together when 5 V appears. Each can supply up to 1 A.

!!! warning
    The 3.3 V on header pin 2 comes from the same regulator as the rest of the board. Keep cape loads modest; a short on pin 2 takes the whole board down.

## No battery backup

The processor's backup domain (real-time clock) runs from the 1.2 V rail, so the clock doesn't keep time while the board is unpowered.
