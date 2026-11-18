# Known issues

Problems in revision 2.0 that can affect you, and what to do about them. All are tracked on [GitHub](https://github.com/vd-rd/sbc_at91sam9g10/issues); fixes go into the next revision.

| Issue | What you notice | Workaround |
|---|---|---|
| Boot needs a small microSD card | Cards over 2 GB don't boot | Use a 2 GB (SDSC) card for booting |
| [Possible boot hang at power-up (#6)](https://github.com/vd-rd/sbc_at91sam9g10/issues/6) | The board may not start after power-up (processor erratum on the NTRST pin) | Power-cycle the board |
| [No I²C pull-ups (#7)](https://github.com/vd-rd/sbc_at91sam9g10/issues/7) | I²C devices on the header aren't detected | Add 4.7 kΩ pull-ups from SDA and SCL to 3.3 V on your cape |
| [GPIO3/GPIO4 driven at boot (#12)](https://github.com/vd-rd/sbc_at91sam9g10/issues/12) | Header pins 19 and 24 toggle or are driven before Linux runs | Don't connect outputs from a cape to these pins, or add a 1 kΩ series resistor |
| [Reset pulse too short (#13)](https://github.com/vd-rd/sbc_at91sam9g10/issues/13) | After a software reboot, devices on the RESET pin and the DataFlash aren't reset | Power-cycle if a cape needs a clean reset |
| microSD card detect polarity | Card insert/remove not detected in Linux | In the device tree, card detect (PA11) is **active high** |
