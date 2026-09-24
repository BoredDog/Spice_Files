# bjt

<!-- generated file -->

Bipolar junction transistors (BJTs): current-controlled amplifiers and switches.

**Choosing one**
- **Small signal (≤ 200 mA):** amplifiers, logic-level switches, current mirrors. Use 2N3904 / 2N3906 (US parts) or BC547 / BC557 (European). For SMD boards use PMBT3904, BC847 or BC857.
- **Medium current (0.5–1 A):** relay and LED-string drivers. Use BC337 / BC327, BC817 / BC807, PN2222A / PN2907A or BD135–BD140.
- **Power (3–10 A):** motors, lamps, audio output stages. Use TIP31C / TIP32C, TIP41C / TIP42C, MJE3055T or 2N3055.
- **Darlington:** very high gain, so a microcontroller pin can drive amps directly. Use TIP120 / TIP122. Expect a ~0.8–1 V higher V_CE(sat).
- **Gain groups:** the A/B/C suffix on BC5xx parts is the hFE group printed on the transistor. Simulate the one you actually have.

**Which file for the same part?** Prefer the manufacturer file (`_OnSemi`, `_Nexperia`, `_Vishay`) over the `_LTspice` / `_LTwiki` simple models. The simple ones are fine for quick checks but can differ a lot: 2N3904 hFE is 311 in the LTspice model and 146 in the datasheet fit.

**Usage:** `.model` parts use `Q1 c b e <model>`. Subcircuit parts (TIP120, Zetex `_ZX`) use `X1 c b e <name>`. Check the pin order in the file's `@pins:` line.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [2N3055A_OnSemi.lib](2N3055A_OnSemi.lib) | 2N3055A (Q2n3055a) | 2N3055 with 100 V rating | higher-voltage 2N3055 applications | BOTH | [link](https://octopart.com/search?q=2N3055A) |
| [2N3055H_OnSemi.lib](2N3055H_OnSemi.lib) | 2N3055H (Q2n3055h) | high-reliability 2N3055 variant | when your part is marked 2N3055H | BOTH | [link](https://octopart.com/search?q=2N3055) |
| [2N3055_OnSemi.lib](2N3055_OnSemi.lib) | 2N3055 (Q2n3055) | NPN power 60 V 15 A, TO-3 (onsemi) | linear power supplies, audio amplifier output stages | BOTH | [link](https://octopart.com/search?q=2N3055) |
| [2N3904-2N3906-BC546_Datasheet.lib](2N3904-2N3906-BC546_Datasheet.lib) | 2N3904_FCS, 2N3906_FCS, BC546 | datasheet-fitted small-signal NPN/PNP (Fairchild/National) | you want the more detailed Fairchild fit (hFE ~150 at 1.5 mA) instead of the LTspice one | BOTH | [link](https://octopart.com/search?q=2N3904) |
| [2N3904_OnSemi.lib](2N3904_OnSemi.lib) | 2N3904 (Q2n3904) | onsemi's own NPN small-signal model, 40 V 200 mA | default choice for 2N3904 amplifier/switch labs | BOTH | [link](https://octopart.com/search?q=2N3904) |
| [2N3906_OnSemi.lib](2N3906_OnSemi.lib) | 2N3906 (q2n3906) | onsemi's own PNP complement of 2N3904 | PNP side of push-pull / current mirrors with 2N3904 | BOTH | [link](https://octopart.com/search?q=2N3906) |
| [2N4401-2N4403-2N5551-2N5401_LTwiki.lib](2N4401-2N4403-2N5551-2N5401_LTwiki.lib) | 2N4401, 2N4403, 2N5551, 2N5401 | NPN/PNP 40 V 600 mA pair (4401/4403) and 150-160 V pair (5551/5401) | switching; 5551/5401 for high-voltage small-signal (audio drivers, CRT/tube circuits) | BOTH-compat | [link](https://octopart.com/search?q=2N5551) |
| [2SC5200-2SA1943-2SC1815-2SA1015_LTwiki.lib](2SC5200-2SA1943-2SC1815-2SA1015_LTwiki.lib) | 2SC5200, 2SA1943, 2SC1815, 2SA1015 | Toshiba audio power pair 230 V 15 A (5200/1943) and small-signal pair (1815/1015) | audio amplifier output stages; Asian-kit small-signal parts | BOTH-compat | [link](https://octopart.com/search?q=2SC5200) |
| [BC107-BC108-BC109-BC177_Zetex.lib](BC107-BC108-BC109-BC177_Zetex.lib) | BC107BP_ZX, BC108BP_ZX, BC109BP_ZX, BC177AP_ZX | metal-can TO-18 NPN (BC107-109) and PNP (BC177) classics | Indian university lab experiments (CE amplifier, biasing) | BOTH | [link](https://www.diodes.com/part/view/BC107) |
| [BC327_Vishay.lib](BC327_Vishay.lib) | BC327 (Qbc327) | PNP 45 V 800 mA general-purpose | medium-current PNP switching; complement of BC337 | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BC327) |
| [BC337_Vishay.lib](BC337_Vishay.lib) | BC337 (Qbc337) | NPN 45 V 800 mA general-purpose | relay/LED drivers needing more current than BC547 | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BC337) |
| [BC546-BC559_LTwiki.lib](BC546-BC559_LTwiki.lib) | BC546A...BC559C | BC54x/BC55x NPN/PNP family in A/B/C gain groups (ltwiki copy of LTspice lines) | European small-signal parts; pick the gain letter printed on your transistor | BOTH-compat | [link](https://www.nexperia.com/product/BC847) |
| [BC546-BC560_Zetex.lib](BC546-BC560_Zetex.lib) | BC546BP_ZX...BC560AP_ZX | Zetex/Diodes models for BC546-BC560 | second opinion on BC5xx behaviour; subckt form with package parasitics | BOTH | [link](https://www.diodes.com/part/view/BC547B) |
| [BC547B_OnSemi.lib](BC547B_OnSemi.lib) | BC547B (Qbc547b) | NPN 45 V 100 mA small-signal, hFE 200-450 (onsemi) | default BC547B: small-signal amplifiers and switches | BOTH | [link](https://octopart.com/search?q=BC547B) |
| [BC557B_OnSemi.lib](BC557B_OnSemi.lib) | BC557B (Qbc557b) | PNP 45 V 100 mA small-signal, complement of BC547B | PNP side of BC547/BC557 circuits | BOTH | [link](https://octopart.com/search?q=BC557B) |
| [BC807_Vishay.lib](BC807_Vishay.lib) | BC807 (Qbc807) | PNP 45 V 500 mA SMD (SOT-23) | SMD complement of BC817 | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=BC807) |
| [BC817-25_Nexperia.lib](BC817-25_Nexperia.lib) | BC817_25 | NPN 45 V 500 mA SMD, hFE 160-400 | SMD replacement for BC337-25 | BOTH | [link](https://www.nexperia.com/product/BC817-25) |
| [BC817-40_Nexperia.lib](BC817-40_Nexperia.lib) | BC817_40 | NPN 45 V 500 mA SMD, hFE 250-600 | SMD replacement for BC337-40 | BOTH | [link](https://www.nexperia.com/product/BC817-40) |
| [BC847_Nexperia.lib](BC847_Nexperia.lib) | BC847 | NPN 45 V 100 mA SMD small-signal | SMD equivalent of BC547 (Nexperia vendor model) | BOTH | [link](https://www.nexperia.com/product/BC847) |
| [BC857_Nexperia.lib](BC857_Nexperia.lib) | BC857 | PNP 45 V 100 mA SMD small-signal | SMD equivalent of BC557 | BOTH | [link](https://www.nexperia.com/product/BC857) |
| [BD135-BD140_Philips.lib](BD135-BD140_Philips.lib) | BD135...BD140 | medium-power NPN (odd) / PNP (even) 45-80 V 1.5 A, TO-126 | audio driver stages, small motor/relay drivers | BOTH | [link](https://octopart.com/search?q=BD139) |
| [MJE3055T_OnSemi.lib](MJE3055T_OnSemi.lib) | MJE3055T | NPN power 60 V 10 A, TO-220 | power stages, linear regulators pass element | BOTH | [link](https://octopart.com/search?q=MJE3055T) |
| [PMBT3904_Nexperia.lib](PMBT3904_Nexperia.lib) | PMBT3904 | NPN 40 V 200 mA SMD (SOT-23) | SMD version of 2N3904 | BOTH | [link](https://www.nexperia.com/product/PMBT3904) |
| [PN2222A-PN2907A_Fairchild.lib](PN2222A-PN2907A_Fairchild.lib) | PN2222A, PN2907A | NPN/PNP 40 V 600-800 mA, TO-92 | complementary pair for push-pull and H-bridge demos | BOTH | [link](https://octopart.com/search?q=PN2222A) |
| [TIP120_OnSemi.lib](TIP120_OnSemi.lib) | TIP120 (subckt) | NPN Darlington 60 V 5 A with built-in resistors and diode | driving motors/solenoids straight from a microcontroller pin | BOTH | [link](https://octopart.com/search?q=TIP120) |
| [TIP122_OnSemi.lib](TIP122_OnSemi.lib) | TIP122 (subckt) | NPN Darlington 100 V 5 A | same as TIP120, higher voltage | BOTH | [link](https://octopart.com/search?q=TIP122) |
| [TIP29-TIP32-TIP2955-TIP3055_OnSemi.lib](TIP29-TIP32-TIP2955-TIP3055_OnSemi.lib) | TIP29C, TIP30C, TIP31, TIP31A, TIP32, TIP32A, TIP32C, TIP2955, TIP3055 | TIP power BJT family (onsemi via Micro-Cap) | power switching / class-AB output stages | BOTH | [link](https://octopart.com/search?q=TIP31C) |
| [TIP31C_Motorola.lib](TIP31C_Motorola.lib) | tip31c | NPN power 100 V 3 A (legacy Motorola model) | only if you need to compare with the onsemi TIP31C | BOTH | [link](https://octopart.com/search?q=TIP31C) |
| [TIP31C_OnSemi.lib](TIP31C_OnSemi.lib) | TIP31C (Qtip31c) | NPN power 100 V 3 A, TO-220 (onsemi) | default TIP31C | BOTH | [link](https://octopart.com/search?q=TIP31C) |
| [TIP41C_OnSemi.lib](TIP41C_OnSemi.lib) | TIP41C (Qtip41c) | NPN power 100 V 6 A, TO-220 | heavier-current version of TIP31C | BOTH | [link](https://octopart.com/search?q=TIP41C) |
| [TIP42C_OnSemi.lib](TIP42C_OnSemi.lib) | TIP42C (Qtip42c) | PNP power 100 V 6 A, complement of TIP41C | PNP half of a TIP41C/TIP42C push-pull stage | BOTH | [link](https://octopart.com/search?q=TIP42C) |
| [standard-bjt_LTspice.lib](standard-bjt_LTspice.lib) | 2N2222, 2N2907, 2N3904, 2N3906, BC547B/C, BC557B, BC337-25, BC327-25, 2N3055 | LTspice's built-in simple BJT models | quick first simulations; matches what LTspice uses by default | BOTH-compat | [link](https://octopart.com/search?q=2N3904) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
