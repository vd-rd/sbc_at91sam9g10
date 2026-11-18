# Boot & recovery

How the board finds its software at power-up, and what to do when it doesn't.

## Boot chain

1. **Boot ROM** — built into the processor. Looks for a bootloader on the boot media (below).
2. **AT91Bootstrap** — the first-stage bootloader (`boot.bin`). Sets up the SDRAM and clocks, then loads U-Boot.
3. **U-Boot** — loads the Linux kernel and device tree.
4. **Linux**.

## Where the boot ROM looks

The boot ROM tries these in order and runs the first valid bootloader it finds:

1. SPI flash on the processor's SPI0 bus — **not fitted** on this board.
2. NAND flash — **not fitted**.
3. **microSD card** — looks for `boot.bin` in the root of a FAT-formatted card.
4. I²C EEPROM at address 0x50 — not fitted (a cape could provide one).
5. If nothing is found: **recovery mode (SAM-BA)**.

!!! note "microSD card size"
    The boot ROM only reads **standard-capacity (SDSC) cards, up to 2 GB**. Larger SDHC/SDXC cards are not recognised at this stage. Once U-Boot and Linux are running, they can use larger cards.

The on-board DataFlash (U5) is on a different SPI bus (SPI1), so the boot ROM can't boot from it. Linux and U-Boot can still use it for data.

## Recovery mode (SAM-BA)

With no bootable card inserted, the processor waits for a computer on either:

- the **USB-C port**, or
- the **debug console** (header J4 pins 11/12, 115200 baud).

Microchip's SAM-BA tool can then load and run software in the processor's internal memory. This is how you recover a board without a working card.
