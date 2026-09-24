# regulators

<!-- generated file -->

Voltage regulators and references.

- **Fixed linear:** LM7805 / 7812 / 7815 (positive) and LM7905 (negative). Need about 2 V of headroom.
- **Adjustable:** LM317 (positive, 1.25–37 V) and LM337 (negative). Set the output with two resistors.
- **Low-dropout:** LM1117. Only the 2.85 V fixed version is modelled.
- **Shunt reference / feedback:** TL431, adjustable 2.5–36 V. Also the error amplifier in most off-line SMPS, driving an optocoupler.
- **High voltage:** LR8 (up to 450 V input; ngspice only).
- Regulators need input and output capacitors in simulation as well as on the bench, or they may oscillate.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [LM1086-3P3_TI.lib](LM1086-3P3_TI.lib) | LM1086-3P3_TRANS (INPUT GND OUTPUT) | 1.5 A LDO, 3.3 V | 3.3 V rails; stand-in for AMS1117-3.3 | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm1086.pdf) |
| [LM1086-5P0_TI.lib](LM1086-5P0_TI.lib) | LM1086-5P0_TRANS (INPUT GND OUTPUT) | 1.5 A LDO, 5 V | 5 V rails with low dropout | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm1086.pdf) |
| [LM1086-ADJ_TI.lib](LM1086-ADJ_TI.lib) | LM1086-ADJ_TRANS (INPUT ADJ OUTPUT_0 OUTPUT_1) | 1.5 A LDO, adjustable | custom rail voltages | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm1086.pdf) |
| [LM1117_TI.lib](LM1117_TI.lib) | LM1117_N_2P85_TRANS | 800 mA LDO, 2.85 V fixed version | low-dropout supply rails (only 2.85 V version modelled) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lm1117.pdf) |
| [LM2576_TI.lib](LM2576_TI.lib) | LM2576_TRANS (VIN OUT GND FB ON_OFF_N) | 3 A step-down (buck) switching regulator, 52 kHz | efficient 5/12 V rails from 12-40 V (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lm2576.pdf) |
| [LM2596-12P0_TI.lib](LM2596-12P0_TI.lib) | LM2596_12P0_TRANS (VIN FB OUT GND ON_OFF_N) | 3 A buck regulator, fixed 12 V, 150 kHz | the common buck module (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lm2596.pdf) |
| [LM2596-3P3_TI.lib](LM2596-3P3_TI.lib) | LM2596_3P3_TRANS | 3 A buck regulator, fixed 3.3 V | 3.3 V rails from 12 V (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lm2596.pdf) |
| [LM2596-5P0_TI.lib](LM2596-5P0_TI.lib) | LM2596_5P0_TRANS | 3 A buck regulator, fixed 5 V | 5 V rails from 12-24 V (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lm2596.pdf) |
| [LM2940-10_TI.lib](LM2940-10_TI.lib) | LM2940-N_10P0_TRANS | 1 A LDO, 10 V version | automotive-style LDO (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/lm2940-n.pdf) |
| [LM317_TI.lib](LM317_TI.lib) | LM317_TRANS (IN ADJ OUT_0 OUT_1) | adjustable positive regulator 1.25-37 V 1.5 A | adjustable bench-supply labs | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm317.pdf) |
| [LM337_Bordodynov.lib](LM337_Bordodynov.lib) | LM337-1 | adjustable negative regulator | negative rails with LM317 | BOTH | [link](https://octopart.com/search?q=LM337) |
| [LM4040-2V5_TI.lib](LM4040-2V5_TI.lib) | LM4040_NA2P5 (V+ V-) | 2.5 V precision shunt reference | ADC/DAC references | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/lm4040-n.pdf) |
| [LM723_Bordodynov.lib](LM723_Bordodynov.lib) | LM723 | classic adjustable regulator (2-37 V) with reference | bench-supply design labs | BOTH | [link](https://www.ti.com/lit/ds/symlink/lm723.pdf) |
| [LM78xx_Bordodynov.lib](LM78xx_Bordodynov.lib) | LM7805, 7806, 7808, 7809, 7812, 7815 | fixed positive linear regulators | 5/12 V supply labs | BOTH | [link](https://octopart.com/search?q=LM7805) |
| [LM79xx_Bordodynov.lib](LM79xx_Bordodynov.lib) | LM7905 | fixed negative regulator -5 V |  | BOTH | [link](https://octopart.com/search?q=LM7905) |
| [LR8_ngspice.lib](LR8_ngspice.lib) | LR8ng | high-voltage (450 V) adjustable regulator | offline/high-voltage supplies (NG-only) | NG-only | [link](https://octopart.com/search?q=LR8) |
| [TL431_TI.lib](TL431_TI.lib) | TL431 | adjustable shunt reference 2.5-36 V | references, SMPS feedback with optocouplers | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/tl431.pdf) |
| [UA78L05_TI.lib](UA78L05_TI.lib) | UA78L_5V_TRANS (IN OUT COMMON) | 100 mA 5 V linear regulator (78L05, TO-92) | small 5 V rails (ngspice only) | NG-compat-only | [link](https://www.ti.com/lit/ds/symlink/ua78l.pdf) |
| [UCC28C43_TI.lib](UCC28C43_TI.lib) | UCC28C43_STEADY | current-mode PWM controller (UC3843 family) | flyback/boost SMPS labs | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ucc28c43.pdf) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
