# Software

The board runs Linux, started by two bootloaders. All the software is open source and maintained by [printarescu-labs](https://github.com/printarescu-labs).

| Stage | What it does | Source |
|---|---|---|
| Boot ROM | Built into the processor; finds `boot.bin` on the microSD card | — |
| AT91Bootstrap | First-stage bootloader (`boot.bin`): sets up clocks and SDRAM, loads U-Boot | [vnd_microchip_at91bootstrap3](https://github.com/printarescu-labs/vnd_microchip_at91bootstrap3) |
| U-Boot | Loads the kernel and device tree | [u-boot](https://github.com/printarescu-labs/u-boot) |
| Linux | Mainline kernel with the board's device tree | [linux](https://github.com/printarescu-labs/linux) |
| Image | Builds a complete microSD image | [glasnost-distro-packer](https://github.com/printarescu-labs/glasnost-distro-packer) |

See [Boot & recovery](../hardware-ref/boot.md) for how the processor picks its boot media, and [Compile from source](compile-from-source.md) to build each stage.

!!! note
    Prebuilt images aren't published yet.
