# drivers

<!-- generated file -->

Drivers: parts that let a small logic signal switch a big load.

- **Darlington arrays (ULN2003):** seven open-collector sinks with built-in flyback diodes. The standard way to drive relays, stepper motors and LED strings from a microcontroller. ULN2803 is the 8-channel version of the same cell.
- **Low-side gate drivers (TC4420 / TC4427):** turn a logic pulse into amps of gate current, so a power MOSFET switches in nanoseconds instead of sitting half-on.
- **Half-bridge / high-side gate drivers (IR2110, IR2104, UCC27211, LM5109B):** drive the top MOSFET of a bridge using a bootstrap capacitor. Used for H-bridges, inverters and synchronous buck converters.
- **Motor-driver ICs:** L293D, L298N, DRV8833, A4988 and TB6612 have **no public SPICE model**. Build them from MOSFETs plus a gate driver, or model them behaviourally.
- Gate drivers need their bootstrap and decoupling capacitors in the simulation too, or they won't start.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [IR2110-IR2104_Bordodynov.lib](IR2110-IR2104_Bordodynov.lib) | IR2110, IR2104 | high/low-side MOSFET/IGBT gate drivers (bootstrap) | H-bridges, inverters, synchronous buck; forum reports convergence issues | BOTH-compat | [link](https://octopart.com/search?q=IR2110) |
| [LM5109B_TI.lib](LM5109B_TI.lib) | LM5109B_TRANS | 100 V 1 A half-bridge gate driver | modern IR2110 alternative (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lm5109b.pdf) |
| [TC4420-TC4427_Microchip.lib](TC4420-TC4427_Microchip.lib) | TC4420_I2D_B, TC4427_I2D_A | 6 A single / 1.5 A dual low-side MOSFET drivers | driving power-MOSFET gates from logic in SMPS | BOTH-compat | [link](https://www.microchip.com/en-us/product/TC4420) |
| [UCC27211_TI.lib](UCC27211_TI.lib) | UCC27211 | 120 V 4 A half-bridge gate driver | high-frequency half-bridges | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ucc27211.pdf) |
| [ULN2003_Bordodynov.lib](ULN2003_Bordodynov.lib) | ULN2003 (B1-B7, E, COM, C7-C1) | 7-channel Darlington sink driver with flyback diodes | stepper motors, relays, LED strings from a microcontroller (ULN2803 = 8 channels, same cell) | BOTH | [link](https://www.ti.com/lit/ds/symlink/uln2003a.pdf) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
