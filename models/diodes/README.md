# diodes

<!-- generated file -->

Diodes: rectifiers, signal diodes, Schottky diodes, zeners, LEDs and bridges.

**Choosing one**
- **Mains / transformer rectification (1 A):** 1N4001–1N4007. Pick the voltage rating (4007 = 1000 V). Full-wave bridges: W04G, 2W04G, DF04M or the generic `BRIDGE_GEN`.
- **Fast small-signal:** 1N4148 (clamps, detectors, logic). The onsemi/Nexperia files are vendor models; `D1N4148_PSpiceEval` includes reverse breakdown.
- **Schottky (low drop, fast):** 1N5819 (1 A, DC-DC converters), BAT54 / BAT85 (small signal).
- **Zeners (voltage references / clamps):** the suffix is the voltage (C5V1 = 5.1 V).
  - 1N47xxA: 1 W.
  - BZX55 / BZX79: 0.5 W through-hole.
  - BZX84: SOT-23.
  - BZX85: 1.3 W.

  Simulate at the datasheet test current Izt.
- **LEDs:** `standard-diodes_LTspice` (red QTLP690C, white NSPW500BS, blue LedBLUE) or `LED_RED_GEN` / `LED_GREEN_GEN`.

**Pin order:** `.model` diodes are `D1 anode cathode <model>`. Subcircuit zeners are usually `X1 anode cathode <name>`, but check `@pins`: Vishay BZX84C5V6 is cathode first.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [1N400x_DiodesInc.lib](1N400x_DiodesInc.lib) | DI_1N4001...DI_1N4007 | 1 A general-purpose rectifiers, 50-1000 V | mains/transformer rectifiers, reverse-polarity protection | BOTH | [link](https://www.diodes.com/part/view/1N4007) |
| [1N4148WS_Vishay.lib](1N4148WS_Vishay.lib) | d1n4148ws | 1N4148 in SOD-323, Vishay model with reverse recovery | SMD signal diode; reverse-recovery studies | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=1N4148WS) |
| [1N4148_Nexperia.lib](1N4148_Nexperia.lib) | 1N4148 (subckt) | fast small-signal switching diode (Nexperia model) | clamps, logic, detectors; vendor model | BOTH | [link](https://www.nexperia.com/product/1N4148) |
| [1N4148_OnSemi.lib](1N4148_OnSemi.lib) | D1N4148 | fast small-signal switching diode (onsemi model) | same use as above; onsemi parameters | BOTH | [link](https://octopart.com/search?q=1N4148) |
| [1N47xxA_DiodesInc.lib](1N47xxA_DiodesInc.lib) | DI_1N4728A...DI_1N4764A | 1 W zener diodes 3.3-100 V (pins: 1 anode, 2 cathode) | shunt regulators and voltage references; pick the voltage from the datasheet table | BOTH | [link](https://www.diodes.com/part/view/1N4733A) |
| [1N5231B_DiodesInc.lib](1N5231B_DiodesInc.lib) | 1N5231B | 0.5 W zener 5.1 V (1N52xxB series) | 5.1 V reference/clamp (US-style part numbers) | BOTH | [link](https://www.diodes.com/part/view/1N5231B) |
| [1N5406-1N5408-1N5711WS_DiodesInc.lib](1N5406-1N5408-1N5711WS_DiodesInc.lib) | DI_1N5406, DI_1N5408, DI_1N5711WS | 3 A rectifiers (600/1000 V) and small RF Schottky | higher-current supply rectifiers; 1N5711 for RF detectors | BOTH | [link](https://www.diodes.com/part/view/1N5408) |
| [1N5819_OnSemi.lib](1N5819_OnSemi.lib) | D1n5819 | 1 A 40 V Schottky | low-drop rectification in DC-DC converters, OR-ing | BOTH | [link](https://octopart.com/search?q=1N5819) |
| [2W04G-W04G-DF04M_Bordodynov.lib](2W04G-W04G-DF04M_Bordodynov.lib) | 2W04G, W04G, DF04M | bridge rectifiers (4 diodes in one package), 400 V 1.5-2 A | full-wave rectifier in power-supply labs | BOTH | [link](https://octopart.com/search?q=W04G) |
| [BAT54_Nexperia.lib](BAT54_Nexperia.lib) | BAT54 (subckt) | 30 V 200 mA small Schottky (SOT-23) | low-drop signal rectification, clamps | BOTH | [link](https://www.nexperia.com/product/BAT54) |
| [BAT85_Vishay.lib](BAT85_Vishay.lib) | bat85 | 30 V 200 mA Schottky, DO-34 glass | through-hole small Schottky | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BAT85) |
| [BZX55C24_Vishay.lib](BZX55C24_Vishay.lib) | bzx55c24 | 0.5 W zener, 24 V | 24 V reference/clamp | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BZX55C24) |
| [BZX55C3V9_Vishay.lib](BZX55C3V9_Vishay.lib) | bzx55c3v9 | 0.5 W zener, 3.9 V | 3.9 V reference | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BZX55C3V9) |
| [BZX55C5V1_Vishay.lib](BZX55C5V1_Vishay.lib) | bzx55c5v1 | 0.5 W zener, 5.1 V | 5.1 V reference / clamp for 5 V logic inputs | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BZX55C5V1) |
| [BZX55C9V1_Vishay.lib](BZX55C9V1_Vishay.lib) | bzx55c9v1 | 0.5 W zener, 9.1 V | 9.1 V reference | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BZX55C9V1) |
| [BZX55_Vishay.lib](BZX55_Vishay.lib) | BZX55C2V7...BZX55C68 | BZX55 zener series (10 values) via Micro-Cap | when your value is not in a single-part Vishay file | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BZX55) |
| [BZX79-C2V4_Nexperia.lib](BZX79-C2V4_Nexperia.lib) | BZX79-C2V4 | 0.5 W zener, 2.4 V | low-voltage reference | BOTH | [link](https://www.nexperia.com/product/BZX79-C2V4) |
| [BZX79-C6V8_Nexperia.lib](BZX79-C6V8_Nexperia.lib) | BZX79-C6V8 | 0.5 W zener, 6.8 V (lowest temperature coefficient region) | stable references | BOTH | [link](https://www.nexperia.com/product/BZX79-C6V8) |
| [BZX84-B12_Nexperia.lib](BZX84-B12_Nexperia.lib) | BZX84-B12 | SOT-23 zener, 12 V, 2 % tolerance | SMD 12 V reference | BOTH | [link](https://www.nexperia.com/product/BZX84-B12) |
| [BZX84-B15_Nexperia.lib](BZX84-B15_Nexperia.lib) | BZX84-B15 | SOT-23 zener, 15 V, 2 % | SMD 15 V reference | BOTH | [link](https://www.nexperia.com/product/BZX84-B15) |
| [BZX84-B6V2_Nexperia.lib](BZX84-B6V2_Nexperia.lib) | BZX84-B6V2 | SOT-23 zener, 6.2 V, 2 % | SMD 6.2 V reference | BOTH | [link](https://www.nexperia.com/product/BZX84-B6V2) |
| [BZX84C16_Vishay.lib](BZX84C16_Vishay.lib) | bzx84c16 | SOT-23 zener, 16 V | SMD 16 V reference | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BZX84C16) |
| [BZX84C5V6_Vishay.lib](BZX84C5V6_Vishay.lib) | bzx84_c5v6 | SOT-23 zener, 5.6 V (pins: 2 cathode first, then 1) | SMD 5.6 V; note the pin order | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BZX84C5V6) |
| [BZX85C15_Vishay.lib](BZX85C15_Vishay.lib) | bzx85c15 | 1.3 W zener, 15 V | higher-power 15 V shunt | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BZX85C15) |
| [D1N4148_PSpiceEval.lib](D1N4148_PSpiceEval.lib) | D1N4148 | PSpice EVAL 1N4148 with 100 V breakdown | when reverse breakdown matters | BOTH | [link](https://octopart.com/search?q=1N4148) |
| [GLL4747_Vishay.lib](GLL4747_Vishay.lib) | gll4747 | 1 W zener 20 V (MELF, 1N4747A equivalent) | 20 V reference | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=GLL4747) |
| [P6KE6V8A_ST.lib](P6KE6V8A_ST.lib) | P6KE6V8A (Anode Cathode) | 600 W unidirectional TVS, 6.8 V | surge/ESD protection on 5 V lines | BOTH | [link](https://octopart.com/search?q=P6KE6.8A) |
| [SMBJ5.0A_Vishay.lib](SMBJ5.0A_Vishay.lib) | SMBJ5_0A | 600 W SMB TVS, 5 V standoff | surge protection of 5 V rails (SMD) | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=SMBJ5.0A) |
| [UF4007-DF10M_KiCadLib.lib](UF4007-DF10M_KiCadLib.lib) | UF4007, DI_DF10M | ultra-fast 1 A 1000 V rectifier; 1 A 1000 V bridge (DF10M) | UF4007: SMPS/flyback snubbers; DF10M: compact bridge rectifier | BOTH-compat | [link](https://octopart.com/search?q=UF4007) |
| [generic-diodes_Repo.lib](generic-diodes_Repo.lib) | LED_RED_GEN, LED_GREEN_GEN, 1N4733A_GEN, 1N4742A_GEN, DRECT_GEN, BRIDGE_GEN | repo-written teaching models | quick LED/zener/bridge circuits that must run everywhere | BOTH | — |
| [standard-diodes_LTspice.lib](standard-diodes_LTspice.lib) | 1N4148, 1N914, 1N4007, 1N5817-19, BAT54, 1N750, BZX84C12L, QTLP690C, NSPW500BS, 1N34A, LedBLUE, LedWHITE | LTspice's built-in diode models | matching what LTspice uses by default; LEDs | BOTH-compat | [link](https://octopart.com/search?q=1N4148) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
