# thyristors

<!-- generated file -->

Thyristors: latching switches for AC power control.

- **SCR (2N6394):** a gate pulse turns it on, and it stays on until the current falls to zero. Used for phase control and crowbar protection. This model runs in LTspice only.
- **Triac (BT136):** a bidirectional SCR, for AC light dimmers and motor speed control.
- **Diac (DB3):** breaks over at ~32 V. Classic triac trigger in dimmer circuits.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [2N5060_Bordodynov.lib](2N5060_Bordodynov.lib) | 2N5060 (anode gate cathode) | sensitive-gate SCR 30 V 0.8 A | low-current SCR labs (LTspice only) | LT-only | [link](https://octopart.com/search?q=2N5060) |
| [2N6394_Bordodynov.lib](2N6394_Bordodynov.lib) | 2N6394 (anode gate cathode) | SCR 50 V 12 A | phase control, crowbars (LTspice only) | LT-only | [link](https://octopart.com/search?q=2N6394) |
| [BT136_KiCadLib.lib](BT136_KiCadLib.lib) | BT136-600, BT136-800 | triac 4 A 600/800 V | AC light dimmers, motor speed control | BOTH | [link](https://octopart.com/search?q=BT136) |
| [BTA16-600B_ST.lib](BTA16-600B_ST.lib) | BTA16-600B (A K G) | 16 A 600 V triac | AC motor/heater control | BOTH-compat | [link](https://octopart.com/search?q=BTA16-600B) |
| [C106D_Bordodynov.lib](C106D_Bordodynov.lib) | C106D | sensitive-gate SCR 400 V 4 A | SCR phase-control labs | BOTH | [link](https://octopart.com/search?q=C106D) |
| [DB3_Bordodynov.lib](DB3_Bordodynov.lib) | DB3 | diac, 32 V breakover | triggering triacs in dimmer circuits | BOTH | [link](https://octopart.com/search?q=DB3) |
| [MAC97A6_Bordodynov.lib](MAC97A6_Bordodynov.lib) | MAC97A6 (MT2 gate MT1) | small 0.6 A 400 V triac, TO-92 | low-power AC switching (LTspice only) | LT-only | [link](https://octopart.com/search?q=MAC97A6) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
