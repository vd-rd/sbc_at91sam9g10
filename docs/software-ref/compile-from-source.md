# Compile from source

How to build each boot stage yourself. You need a Linux computer and an ARM cross-compiler (`arm-none-eabi-` for AT91Bootstrap, `arm-linux-gnueabi-` for U-Boot and Linux).

## AT91Bootstrap

The first-stage bootloader. It runs from the processor's internal memory, sets up the clocks and SDRAM, then loads U-Boot from the microSD card.

```sh
git clone https://github.com/printarescu-labs/vnd_microchip_at91bootstrap3
cd vnd_microchip_at91bootstrap3
export CROSS_COMPILE=arm-none-eabi-
make glasnost_9g10_sd_uboot_defconfig
make
```

Copy the resulting binary from `binaries/` to the root of a FAT-formatted microSD card as **`boot.bin`**. Remember the card must be 2 GB or smaller ([why](../hardware-ref/boot.md)).

!!! note
    The board has no bootable flash, so only the microSD (`sd`) configuration applies.

## U-Boot

Loads the Linux kernel and device tree. Build instructions: to be written.

## Linux kernel

Mainline kernel with the board's device tree. Build instructions: to be written.

## Root filesystem

To be written. The [glasnost-distro-packer](https://github.com/printarescu-labs/glasnost-distro-packer) builds complete images.
