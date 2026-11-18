# Bill of materials

Glasnost boards are meant to be built by others, so the BOM gives **guidance** for each part rather than locking you to one part number: use what you can get, as long as it meets the requirements. A recommended part is given where it helps.

A complete BOM (HTML/PDF, with guidance and recommended parts for every line) will be attached to releases. Until then, the key parts:

| Ref | Part | Requirements |
|---|---|---|
| U1 | AT91SAM9G10-CU | Exact part. 217-ball LFBGA, 0.8 mm pitch. |
| U2, U3 | MT48LC16M16A2 (256 Mbit SDR SDRAM, TSOP-II 54) | x16, 3.3 V, **133 MHz or faster** (speed grade -75 or better). MT48LC32M16 (512 Mbit) fits for 128 MB total. |
| U5 | AT45DB161D | SPI DataFlash, 16 Mbit, SOIC-8. Obsolete — the AT45DB161E successor is the drop-in replacement. |
| U6 | RTL8188CUS USB WiFi module | 6-pad module (GND, USB D+, USB D−, 3.3 V, GND, antenna). Module part number to be documented. |
| U7, U8 | TPS62A01A (SOT-23-6) | Exact part family; the "A" variant (forced PWM) is used. |
| L2, L3 | 1 µH power inductor | Würth MAPI-2512 size; saturation current ≥ 2 A. |
| Y1 | 18.432 MHz crystal, 3225 | Part and load capacitance to be specified. |
| Y2 | 32.768 kHz crystal, 3215 | Part and load capacitance to be specified. |
| J1 | GCT MEM2061-01-188-00-A | microSD, push-push, card-detect switch. |
| J5 | GCT USB4105 | USB-C receptacle, USB 2.0. |
| Passives | 0402 unless noted | Capacitors X5R/X7R; voltage rating ≥ 6.3 V on 3.3 V rails, ≥ 10 V on 5 V. Resistors 1 %. |
