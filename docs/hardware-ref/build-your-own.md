# Build your own

Everything you need to have boards made and assembled. This board is a challenging build: the processor is a fine-pitch BGA and parts sit on both sides.

## Order the PCB

Fabrication files (Gerbers, drill, pick-and-place, BOM) are attached to each [release](https://github.com/vd-rd/sbc_at91sam9g10/releases). The board is designed for JLCPCB's or PCBWay's standard 4-layer process.

| Requirement | Value |
|---|---|
| Layers | 4 ([stackup](pcb.md#stackup)) |
| Thickness | 1.18 mm as designed; order your fab's standard 1.2 mm |
| Minimum track / spacing | 0.11 mm / 0.11 mm |
| Minimum via | 0.45 mm pad, 0.3 mm drill |
| Surface finish | ENIG (recommended for the BGA) |

!!! note
    These requirements haven't yet been checked against each fab's published capabilities.

## Assembly

| | |
|---|---|
| Processor (U1) | 217-ball BGA, 0.8 mm pitch — needs reflow (oven or hot air with care); moisture-sensitive, bake if the bag has been open |
| Sides | Components on both sides: bottom first (decoupling capacitors), then top |
| Through-hole | J3 and J4 (headers), soldered by hand last; J4 is mounted on the **bottom** |
| Smallest passives | 0402 |

If you've never reflowed a BGA, consider having the boards assembled by the fab.

## After assembly

1. Before inserting a card, power the board and check the test points: TP4 ≈ 5 V, TP6 ≈ 3.3 V, TP5 ≈ 1.2 V.
2. Continue with [Getting started](../getting-started.md).
