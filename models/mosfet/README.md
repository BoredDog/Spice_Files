# mosfet

<!-- generated file -->

MOSFETs: voltage-controlled switches, the default choice for switching loads.

**Choosing one**
- **Small signal / logic switching (≤ 0.5 A):** 2N7000 (TO-92), 2N7002 (SOT-23), BS170. For I²C / 3.3 V↔5 V level shifting use BSS138.
- **Logic-level power (fully on at 3.3–5 V gate):** IRLZ44N (47 A), AO3400 (SOT-23, 5.7 A).
- **Standard power (needs ~10 V gate):** IRF540N (100 V), IRFZ44N (55 V), IRF3205 (55 V, 110 A), IRF520.
  - Driving these from a 5 V microcontroller leaves them partly on and hot. Use a gate driver or the IRL part.
- **P-channel (high-side switch):** IRF9540N.

**Which file?** Prefer the `_Infineon` / `_OnSemi` / `_Nexperia` vendor subcircuits. The `standard-vdmos_LTspice` models are simple 3-terminal `.model` lines, which are fine for quick checks. The `_InfineonIR` file has the older IR models, kept for comparison.

**Usage:** VDMOS `.model` parts use `M1 d g s <model>`. Vendor subcircuits use `X1 d g s <name>`; check the pin order in `@pins`, since most are `1=D 2=G 3=S`.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [2N7000-BS170_Zetex.lib](2N7000-BS170_Zetex.lib) | 2N7000_ZX, BS170_ZX | small N-MOSFETs 60 V 200-500 mA (Zetex) | logic-level-ish small switches | BOTH | [link](https://www.diodes.com/part/view/2N7000) |
| [2N7000_OnSemi.lib](2N7000_OnSemi.lib) | 2n7000 (subckt) | N-MOSFET 60 V 200 mA, TO-92 (onsemi) | default 2N7000: LED/relay switching from logic | BOTH | [link](https://octopart.com/search?q=2N7000) |
| [2N7002_Nexperia.lib](2N7002_Nexperia.lib) | 2N7002 (subckt) | N-MOSFET 60 V 300 mA SOT-23 (Nexperia) | SMD version of 2N7000; level shifters | BOTH | [link](https://www.nexperia.com/product/2N7002) |
| [AO3400_AOS.lib](AO3400_AOS.lib) | AO3400 | N-MOSFET 30 V 5.7 A SOT-23, logic-level | low-voltage load switches from 3.3 V logic | BOTH | [link](https://octopart.com/search?q=AO3400) |
| [AO3401A_AOS.lib](AO3401A_AOS.lib) | AO3401A (4=D 1=G 2=S) | P-MOSFET -30 V -4 A SOT-23 | high-side load switch; P-channel partner of AO3400 | BOTH | [link](https://octopart.com/search?q=AO3401A) |
| [BSS138_OnSemi.lib](BSS138_OnSemi.lib) | bss138lt1 | N-MOSFET 50 V 200 mA SOT-23 (onsemi) | default BSS138 (3.3 V <-> 5 V level shifter) | BOTH | [link](https://octopart.com/search?q=BSS138) |
| [IRF3205_Infineon.lib](IRF3205_Infineon.lib) | irf3205 | N-MOSFET 55 V 110 A, 8 mOhm | high-current motor drivers, DC-DC | BOTH | [link](https://octopart.com/search?q=IRF3205) |
| [IRF4905_InfineonIR.lib](IRF4905_InfineonIR.lib) | irf4905 | P-MOSFET -55 V -74 A TO-220 | high-current high-side switches, reverse-polarity protection | BOTH | [link](https://octopart.com/search?q=IRF4905) |
| [IRF540N-IRF9540N-IRFZ44N-IRF3205-IRF520_InfineonIR.lib](IRF540N-IRF9540N-IRFZ44N-IRF3205-IRF520_InfineonIR.lib) | irf540n_IR, irf9540n_IR, irfz44n_IR, irf3205_IR, irf520_IR, irf520n_IR | older International Rectifier power-MOSFET models | comparison with the newer Infineon files | BOTH | [link](https://octopart.com/search?q=IRF540N) |
| [IRF540N_Infineon.lib](IRF540N_Infineon.lib) | irf540n | N-MOSFET 100 V 33 A, 44 mOhm (needs ~10 V gate) | classic lab power MOSFET: motors, lamps, boost converters | BOTH | [link](https://octopart.com/search?q=IRF540N) |
| [IRF9540N_Infineon.lib](IRF9540N_Infineon.lib) | irf9540npbf | P-MOSFET -100 V -23 A | high-side switch, complement of IRF540N | BOTH | [link](https://octopart.com/search?q=IRF9540N) |
| [IRFZ44N_Infineon.lib](IRFZ44N_Infineon.lib) | irfz44n | N-MOSFET 55 V 49 A, 17.5 mOhm | low-voltage high-current switching (10 V gate) | BOTH | [link](https://octopart.com/search?q=IRFZ44N) |
| [IRLZ44N_Infineon.lib](IRLZ44N_Infineon.lib) | irlz44n | logic-level N-MOSFET 55 V 47 A | driving from a 5 V microcontroller pin directly | BOTH | [link](https://octopart.com/search?q=IRLZ44N) |
| [SI2302_Vishay.lib](SI2302_Vishay.lib) | Si2302CDS (D G S) | logic-level N-MOSFET 20 V 2.9 A SOT-23 | switching from 3.3 V logic on small boards | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=SI2302CDS) |
| [standard-vdmos_LTspice.lib](standard-vdmos_LTspice.lib) | 2N7002, IRFZ44N, IRF530, 2N7000 | LTspice-style VDMOS models (3-terminal .model) | fast simple MOSFET sims; 2N7000 line is unverified | BOTH | [link](https://octopart.com/search?q=IRF530) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
