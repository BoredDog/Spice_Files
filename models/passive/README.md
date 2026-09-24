# passive

<!-- generated file -->

Passive and electromechanical parts written for teaching.

- `SW_IDEAL`: voltage-controlled switch (on above 2.6 V).
- `RELAY_SPST_5V`: 5 V relay; pull-in 3.5 V, drop-out 1.5 V.
- `HJR-4102L12`: 12 V SPDT relay with coil-current thresholds.
- `XTAL_16M`: 16 MHz crystal (Butterworth–Van Dyke model), for oscillator labs.
- `XFMR_10TO1`: 10:1 transformer with winding resistance, for rectifier and isolation labs.

These avoid LTspice-only syntax, so they run in both simulators.

## Models in this folder

**Works in:** BOTH = LTspice and native ngspice; BOTH-compat = also ngspice, with the repo `.spiceinit`; NG / LT = one simulator only.

| File | Part(s) / model names | What it is | Use it for | Works in | Datasheet |
|---|---|---|---|---|---|
| [HJR-4102-12V-relay_ngspice.lib](HJR-4102-12V-relay_ngspice.lib) | HJR-4102L12 (COM NO NC POS NEG) | 12 V SPDT relay with coil-current switching | relay-driver labs | BOTH | — |
| [generic-passive_Repo.lib](generic-passive_Repo.lib) | SW_IDEAL, RELAY_SPST_5V, XTAL_16M, XFMR_10TO1 | ideal switch, 5 V relay, 16 MHz crystal, 10:1 transformer | oscillator, isolation and rectifier labs | BOTH | — |

Datasheet links: ti.com links go straight to the PDF (all checked 2026-09-24); nexperia.com and vishay.com links open the product or search page; octopart.com links search for the part and list the official datasheet. Each model file's header (`@url`) says where it was downloaded from.
