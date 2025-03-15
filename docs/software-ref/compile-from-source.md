## Components

This page describes the steps to build an image that can be used with the board, containing a basic linux distribution ready for further hacking.

There are several pieces of software required to put togheter in order to get to an usable shell. Consult the boot documentation for detailed information about the order of execution and relationship between components, but for the purpose of this documentation, the flow looks like this following a board power up:


``` mermaid 
graph LR
A[Embedded ROM] --> B{Find media};
B --> |SD Card| C[AT91Bootstrap];
C --> D[U-Boot];
D --> E[Linux Distro]
B --> |NOR Flash| F[Recovery Distro]
```

The board is equipped with two storage mediums, a NOR Flash soldered on the board and a removable microSD card. the Flash is loaded with a recovery environment suitable for debugging issues. the SD card is loaded with the full flagged distro.


### AT91Bootstrap

This is the second stage loader that is executed by the embedded ROM, after it is found in one of the storage mediums. the loader is executed in the internal SRAM and prepares DRAM, clocks and other peripherals for U-Boot execution. It loads U-Boot and hands over execution. 

For the M9G10 board, a forked AT91Bootstrap is used, where modifications where added to match the hardware configuration. 

In order to compile it first the repo must be cloned and a working arm-none-eabi toolchain must be present.
``` bash
export CROSS_COMPILE=/path/to/arm-none-eabi-
git clone vd-rd/at91bootstrap3
cd AT91Bootstrap
```

The project used menuconfig to select options, akin to Linux kernel and U-Boot. There are two targets that can be selected for the build:
- glasnost_9g10_df_uboot_defconfig
- glasnost_9g10_sd_uboot_defconfig
``` bash
make [target]
make

Binary ready to be used will be found in the binary folder.


### U-Boot
This is the 3rd level bootloader, loaded in the last MB of DRAM that further enables board peripherals, loads device tree and overlays if present and starts the kernel. 


### Kernel

### RootFS
