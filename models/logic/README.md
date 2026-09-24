# logic

<!-- generated file -->

Digital logic (74HC and 74xx families): **ngspice / KiCad only.**

These are event-driven digital models (XSPICE). They simulate very fast but don't run in LTspice. For LTspice use its built-in A-devices (Digital symbols).

- `74HCxxm_ngspice.lib`: one model per 14/16-pin package, pins numbered as on the chip. The supply pins are not used; logic 1 is 3.3 V at the analog interface.
- `74xx_ngspice.lib`: single gates for many families (74, LS, HC, HCT, AC, ALS…).
- To plot a digital node in ngspice, put a 1 MΩ resistor from it to ground; that turns it into an analog node.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [74HC00m_ngspice.lib](74HC00m_ngspice.lib) | 74HC00m | quad 2-input NAND, 14-pin package model (ngspice digital) | digital logic in ngspice/KiCad only | NG-compat-only | [link](https://www.nexperia.com/product/74HC00) |
| [74HC02m_ngspice.lib](74HC02m_ngspice.lib) | 74HC02m | quad 2-input NOR |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC02) |
| [74HC04m_ngspice.lib](74HC04m_ngspice.lib) | 74HC04m | hex inverter |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC04) |
| [74HC08m_ngspice.lib](74HC08m_ngspice.lib) | 74HC08m | quad 2-input AND |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC08) |
| [74HC10m_ngspice.lib](74HC10m_ngspice.lib) | 74HC10m | triple 3-input NAND |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC10) |
| [74HC138m_ngspice.lib](74HC138m_ngspice.lib) | 74HC138m | 3-to-8 line decoder |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC138) |
| [74HC14m_ngspice.lib](74HC14m_ngspice.lib) | 74HC14m | hex Schmitt-trigger inverter |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC14) |
| [74HC20m_ngspice.lib](74HC20m_ngspice.lib) | 74HC20m | dual 4-input NAND |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC20) |
| [74HC283m_ngspice.lib](74HC283m_ngspice.lib) | 74HC283m | 4-bit binary full adder |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC283) |
| [74HC32m_ngspice.lib](74HC32m_ngspice.lib) | 74HC32m | quad 2-input OR |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC32) |
| [74HC36m_ngspice.lib](74HC36m_ngspice.lib) | 74HC36m | quad 2-input NOR (74HC36 pinout) |  | NG-compat-only | [link](https://octopart.com/search?q=74HC36) |
| [74HC74m_ngspice.lib](74HC74m_ngspice.lib) | 74HC74m | dual D flip-flop with set/reset |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC74) |
| [74HC86m_ngspice.lib](74HC86m_ngspice.lib) | 74HC86m | quad 2-input XOR |  | NG-compat-only | [link](https://www.nexperia.com/product/74HC86) |
| [74xx_ngspice.lib](74xx_ngspice.lib) | 7400...74xx (single gates, many families) | gate-level PSpice digital models translated by ngspice | any 74-series gate in ngspice/KiCad (NG-only) | NG-compat-only | — |
| [CD4011B_TI.lib](CD4011B_TI.lib) | CD4011B (Y A B VCC AGND) | one CMOS 2-input NAND gate, behavioural, 3-18 V | gate oscillators, logic labs at 5-15 V | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/cd4011b.pdf) |
| [CD4013-CD4017-CD4040-CD4060_MicroCap.lib](CD4013-CD4017-CD4040-CD4060_MicroCap.lib) | CD4013B, CD4017B, CD4040B, CD4060B | CMOS D flip-flop, decade counter, 12-bit counter, 14-stage counter/oscillator | 555 + 4017 LED chaser, dividers, clocks (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/cd4017b.pdf) |
| [CD4066B_Bordodynov.lib](CD4066B_Bordodynov.lib) | CD4066B | quad bilateral analog switch | signal routing, sample-and-hold | BOTH | [link](https://www.ti.com/lit/ds/symlink/cd4066b.pdf) |
| [CD4093B_TI.lib](CD4093B_TI.lib) | CD4093B (Y A B VCC AGND) | one CMOS Schmitt-trigger NAND, behavioural | RC oscillators, debouncing | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/cd4093b.pdf) |
| [SN74HC00_TI.lib](SN74HC00_TI.lib) | SN74HC00 (Y A B VCC AGND) | one 74HC NAND gate, behavioural (runs in both simulators) | analog-accurate logic edges in LTspice and ngspice | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/sn74hc00.pdf) |
| [SN74HC14_TI.lib](SN74HC14_TI.lib) | SN74HC14 (Y A VCC AGND) | one 74HC Schmitt inverter, behavioural | oscillators, squaring slow signals | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/sn74hc14.pdf) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
