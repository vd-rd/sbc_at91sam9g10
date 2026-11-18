# PCB

| | |
|---|---|
| Size | 66 × 42 mm |
| Layers | 4 |
| Thickness | 1.18 mm (as designed) |
| Finish | ENIG |
| Solder mask / silkscreen | Red / white |
| Components | Both sides (most on top; decoupling capacitors and the main header on the bottom) |

## Stackup

| Layer | Use | Thickness |
|---|---|---|
| F.Cu (top) | Signals, components | 35 µm copper |
| Prepreg | FR408-HR, εr 4.1 | 0.0994 mm |
| In1.Cu | Ground plane | 15 µm copper |
| Core | FR4, εr 4.6 | 0.865 mm |
| In2.Cu | Power plane (3.3 V, with a 1.2 V area under the processor) | 15 µm copper |
| Prepreg | FR408-HR, εr 4.1 | 0.0994 mm |
| B.Cu (bottom) | Signals, components | 35 µm copper |

The PCB file is [`hardware/sbc.kicad_pcb`](https://github.com/vd-rd/sbc_at91sam9g10/blob/main/hardware/sbc.kicad_pcb). Renders: [top](../assets/front.png), [bottom](../assets/back.png).
