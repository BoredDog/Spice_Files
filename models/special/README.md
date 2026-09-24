# special

<!-- generated file -->

Special-function ICs (ngspice-project models).

- **ICL8038:** function generator (sine / square / triangle), for waveform-generator labs. Works in both simulators with the repo `.spiceinit`.
- **LM3914:** 10-LED bar/dot driver, for level meters (ngspice only).
- **LTC1044:** switched-capacitor voltage inverter / doubler, for making −5 V from +5 V (ngspice only).

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [2N2646_Bordodynov.lib](2N2646_Bordodynov.lib) | 2N2646 (E B1 B2 order per file) | unijunction transistor (UJT) | relaxation oscillators, SCR triggering (Indian lab staple; LTspice only) | BOTH | [link](https://octopart.com/search?q=2N2646) |
| [ICL8038_ngspice.lib](ICL8038_ngspice.lib) | ICL8038 | function generator IC (sine/square/triangle) | waveform-generator labs | BOTH-compat | [link](https://octopart.com/search?q=ICL8038) |
| [LM3914_ngspice.lib](LM3914_ngspice.lib) | lm3914 | 10-LED bar/dot display driver | VU meters, level indicators (NG-only) | NG-only | [link](https://www.ti.com/lit/ds/symlink/lm3914.pdf) |
| [LTC1044_ngspice.lib](LTC1044_ngspice.lib) | LTC1044HV | switched-capacitor voltage converter (inverter) | negative supply from +5 V (NG-only) | NG-only | [link](https://www.analog.com/en/products/ltc1044.html) |
| [MC1496_Bordodynov.lib](MC1496_Bordodynov.lib) | MC1496 (14-pin package order) | balanced modulator/demodulator | AM/DSB modulation labs in communication courses | BOTH | [link](https://octopart.com/search?q=MC1496) |
| [XR2206_Bordodynov.lib](XR2206_Bordodynov.lib) | XR2206 | function generator IC (sine/square/triangle, AM/FM) | waveform generators (LTspice only) | LT-only | [link](https://octopart.com/search?q=XR2206) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
