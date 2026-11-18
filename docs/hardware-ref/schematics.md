# Schematics

The schematics are KiCad 10 files in [`hardware/`](https://github.com/vd-rd/sbc_at91sam9g10/tree/main/hardware). Open `sbc.kicad_pro` with KiCad 10 or newer — older versions can't read these files.

| Sheet | File | Contents |
|---|---|---|
| Root | `sbc.kicad_sch` | Block overview, mounting holes, fiducials |
| CPU Signals | `cpu.kicad_sch` | Processor, crystals, PLL filters, reset, boot mode |
| SDRAM | `sdram.kicad_sch` | Two SDRAM chips on the 32-bit memory bus |
| Power rails | `power.kicad_sch` | 3.3 V and 1.2 V regulators, decoupling |
| IO Expansions | `io.kicad_sch` | USB-C, headers J3/J4, LED, buttons |
| SDCard | `sdcard.kicad_sch` | microSD slot, SPI DataFlash |
| Networking | `wifi.kicad_sch` | WiFi module and antenna |

A PDF export of the schematics is attached to each [release](https://github.com/vd-rd/sbc_at91sam9g10/releases).
