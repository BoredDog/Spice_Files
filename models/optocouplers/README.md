# optocouplers

<!-- generated file -->

Optocouplers: an LED and a phototransistor in one package, for passing signals across an isolation barrier.

- **CTR** (current transfer ratio) = I_C / I_LED. It is the key number, and it varies a lot between parts and samples.
- `OPTO_GEN` (set `CTR=`) plus the presets `PC817_GEN`, `4N35_GEN` and `CNY17_GEN` work in both simulators. Use these for PC817 / 4N35 / CNY17 circuits.
- `4N25_LTspice` / `4N27_LTspice`: LTspice's models (pins A K E C B), which work in both.
- For a fast digital output, keep the load resistor small (≈ 1 kΩ). The phototransistor is slow, so expect microseconds.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [4N25_LTspice.lib](4N25_LTspice.lib) | 4N25 (pins A K E C B) | phototransistor optocoupler, CTR ~20 %+ (LTspice) | isolating digital signals | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=4N25) |
| [4N27_LTspice.lib](4N27_LTspice.lib) | 4N27 | phototransistor optocoupler, lower CTR |  | BOTH | [link](https://www.vishay.com/search/?searchChoice=part&query=4N27) |
| [6N137_Bordodynov.lib](6N137_Bordodynov.lib) | 6N137 (A K S C V E) | 10 Mbit/s logic-output optocoupler | isolated UART / fast digital isolation (LTspice only) | LT-only | [link](https://www.vishay.com/search/?searchChoice=part&query=6N137) |
| [MOC3021_Bordodynov.lib](MOC3021_Bordodynov.lib) | MOC3021 | random-phase triac-driver optocoupler | phase-controlled AC dimmers with a triac | BOTH | [link](https://octopart.com/search?q=MOC3021) |
| [MOC3043M_Fairchild.lib](MOC3043M_Fairchild.lib) | MOC3043M (A K MT2 MT1) | zero-crossing triac-driver optocoupler (MOC3041 family) | solid-state relays switching resistive AC loads (LTspice only) | LT-only | [link](https://octopart.com/search?q=MOC3043M) |
| [OPTO-generic_Repo.lib](OPTO-generic_Repo.lib) | OPTO_GEN (CTR=), PC817_GEN, 4N35_GEN, CNY17_GEN | repo-written optocoupler with set CTR (pins A K C E) | PC817/4N35/CNY17 circuits in either simulator | BOTH | [link](https://octopart.com/search?q=PC817) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
