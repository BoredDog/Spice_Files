# timers

<!-- generated file -->

555 / 556 timers: astable oscillators, monostable pulse generators and PWM.

- **Bipolar 555 (NE555-type):** `555bip` (transistor level, both simulators with `.spiceinit`) or the behavioural `NE555` (LTspice only, fast).
- **CMOS 555** (low power, rail-to-rail output, like TLC555 / ICM7555): `CMOS555` (transistor level), or `ICM7555` (LTspice).
- **Dual 556:** `NE556` (LTspice).
- Astable: f ≈ 1.44 / ((Ra + 2Rb)·C). The transistor-level models reproduce this within a few percent (see `tests/ngproj_*555*.cir`).

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [555-CMOS_ngspice.lib](555-CMOS_ngspice.lib) | CMOS555 | transistor-level CMOS 555 | low-power 555 designs (like TLC555/ICM7555) | BOTH | [link](https://www.ti.com/lit/ds/symlink/tlc555.pdf) |
| [555-bipolar_ngspice.lib](555-bipolar_ngspice.lib) | 555bip | transistor-level bipolar 555 | classic NE555 astable/monostable labs | BOTH-compat | [link](https://www.ti.com/lit/ds/symlink/ne555.pdf) |
| [NE555-NE556-LM555-ICM7555_Bordodynov.lib](NE555-NE556-LM555-ICM7555_Bordodynov.lib) | NE555, NE556, LM555, ICM7555 | behavioural 555/556 timers (LTspice only) | fast 555 sims in LTspice | LT-only | [link](https://www.ti.com/lit/ds/symlink/ne555.pdf) |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
